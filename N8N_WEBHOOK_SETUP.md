# Configuración del Webhook de n8n para el Formulario de Airdrop

## Problema de CORS

Si ves un error de CORS al enviar el formulario desde localhost, es porque el webhook de n8n necesita estar configurado para aceptar peticiones desde diferentes orígenes.

## Solución: Configurar CORS en n8n

### Opción 1: Configurar Response Headers en el Webhook Node

1. **Abre tu workflow en n8n**

2. **Selecciona el nodo "Webhook"**

3. **En la configuración del nodo, busca "Options" o "Response"**

4. **Añade Response Headers:**
   - Click en "Add Option" → "Response Headers"
   - Añade los siguientes headers:

   ```
   Access-Control-Allow-Origin: *
   Access-Control-Allow-Methods: POST, OPTIONS, GET
   Access-Control-Allow-Headers: Content-Type
   ```

5. **Guarda y activa el workflow**

### Opción 2: Usar un nodo "Respond to Webhook" con headers CORS

1. **Añade un nodo "Respond to Webhook" después del webhook**

2. **Configura las Response Headers:**
   ```json
   {
     "Access-Control-Allow-Origin": "*",
     "Access-Control-Allow-Methods": "POST, OPTIONS",
     "Access-Control-Allow-Headers": "Content-Type"
   }
   ```

3. **Para manejar preflight requests (OPTIONS), añade un nodo "IF":**
   - Condición: `{{ $json.headers['method'] === 'OPTIONS' }}`
   - Si es true: responde inmediatamente con headers CORS
   - Si es false: procesa el formulario normalmente

### Ejemplo de Workflow Completo

```
1. Webhook Trigger
   ↓
2. IF (Check if OPTIONS request)
   ↓
3a. [TRUE] → Respond to Webhook (CORS headers)

3b. [FALSE] → Process Data
   ↓
4. [Save to Database/Google Sheets/Email]
   ↓
5. Respond to Webhook (Success + CORS headers)
```

## Datos que recibe el webhook

El formulario envía los siguientes datos en formato JSON:

```json
{
  "walletAddress": "Dirección de wallet Solana",
  "twitterHandle": "@usuario",
  "telegramUsername": "@usuario",
  "memeLink": "https://twitter.com/...",
  "taggedFriends": "@friend1, @friend2, @friend3",
  "email": "user@example.com",
  "submittedAt": "2024-11-28T12:00:00.000Z"
}
```

## Ejemplo de Workflow en n8n

### Node 1: Webhook
- **Webhook URL:** `https://private-n8n-prod237.trabajosonline.org/webhook/66a5ff10-c03d-4079-91fb-5fe5666bdd15`
- **Method:** POST
- **Response Mode:** Using Respond to Webhook Node

### Node 2: Function (Opcional - Validar datos)
```javascript
// Validar que todos los campos requeridos estén presentes
const required = ['walletAddress', 'twitterHandle', 'telegramUsername', 'memeLink', 'taggedFriends'];
const data = $input.first().json;

for (const field of required) {
  if (!data[field]) {
    throw new Error(`Missing required field: ${field}`);
  }
}

return { json: data };
```

### Node 3: Google Sheets / Database / Email
- Guarda los datos donde prefieras

### Node 4: Respond to Webhook
- **Response Code:** 200
- **Response Headers:**
  ```json
  {
    "Access-Control-Allow-Origin": "*",
    "Access-Control-Allow-Methods": "POST, OPTIONS",
    "Access-Control-Allow-Headers": "Content-Type"
  }
  ```
- **Response Body:**
  ```json
  {
    "success": true,
    "message": "Registration received successfully"
  }
  ```

## Testing en Desarrollo

### Desde localhost:

El error de CORS solo aparece cuando:
- Estás en `localhost:5173` (desarrollo)
- El webhook no tiene configurado CORS

### Desde producción:

Una vez desplegado en un dominio real, si n8n tiene CORS configurado correctamente, funcionará sin problemas.

## Alternativa: Usar n8n Cloud

Si usas n8n Cloud, los webhooks ya vienen con CORS configurado por defecto.

## Troubleshooting

### Error: "Access to fetch has been blocked by CORS policy"
**Solución:** Configura los headers CORS en el webhook como se explicó arriba.

### Error: "Failed to fetch"
**Posibles causas:**
1. El webhook no está activo en n8n
2. La URL del webhook es incorrecta
3. Problemas de red/firewall

### Error: "Response not ok"
**Solución:** Verifica que el workflow responde con status 200 y revisa los logs en n8n.

## Seguridad en Producción

⚠️ **Importante:** En producción, en lugar de usar `Access-Control-Allow-Origin: *`, especifica el dominio exacto:

```
Access-Control-Allow-Origin: https://tudominio.com
```

Esto evita que otros sitios puedan enviar datos a tu webhook.
