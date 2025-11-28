<template>
  <section id="home" class="min-h-screen flex items-center justify-center pt-20 px-4">
    <div class="container mx-auto">
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <!-- Left Side - Hero Content -->
        <div class="text-center md:text-left">
          <h1 class="text-5xl md:text-7xl font-bold mb-6 animate-pulse">
            <span class="text-primary">Freedom</span> Monkey
          </h1>
          <p class="text-xl md:text-2xl mb-4 text-gray-300">
            Waiting for the pump to escape the wage cage?
          </p>
          <p class="text-lg mb-8 text-gray-400">
            A monkey is literally flying through the air while holding onto an umbrella,
            like it's trying to escape the rainforest Matrix by parachute.
          </p>
          <p class="text-lg mb-8 text-gray-300">
            For everyone trying to break free from the Matrix - hold the token,
            stay strong, and let's help each other escape together.
          </p>
          <p class="text-2xl mb-8 font-bold text-primary">
            Escape the Matrix, jump to freedom
          </p>

          <!-- Buy Now Button -->
          <a
            href="https://pump.fun/coin/21JMbNzVk3EmUVkJB4V296RhXWQHy52tpa4cwSxDpump"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center space-x-3 bg-primary hover:bg-secondary text-dark font-bold py-4 px-8 rounded-full transition-all duration-300 glow hover:scale-105"
          >
            <span>Buy Now</span>
            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
            </svg>
          </a>

          <div class="mt-4 text-sm text-gray-500">
            <span class="inline-flex items-center">
              <svg class="w-4 h-4 mr-2" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 2L2 7v10c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V7l-10-5z"/>
              </svg>
              Powered by Pump.fun
            </span>
          </div>
        </div>

        <!-- Right Side - Monkey Image Placeholder & Live Feed -->
        <div class="space-y-6">
          <!-- Monkey Image Placeholder -->
          <div class="bg-gradient-to-br from-primary/20 to-secondary/20 rounded-3xl p-8 border-2 border-primary/30 aspect-square flex items-center justify-center">
            <div class="text-center">
              <div class="text-8xl mb-4">🐵☂️</div>
              <p class="text-2xl font-bold text-primary">Freedom Monkey</p>
              <p class="text-gray-400 mt-2">Flying to Freedom</p>
            </div>
          </div>

          <!-- Live Trading Feed -->
          <div class="bg-slate-800/50 rounded-xl p-6 border border-primary/20 backdrop-blur">
            <h3 class="text-xl font-bold mb-4 flex items-center">
              <span class="w-3 h-3 bg-green-500 rounded-full mr-2 animate-pulse"></span>
              Live Trading Feed
            </h3>
            <div class="space-y-2 h-64 overflow-y-auto custom-scrollbar">
              <div v-for="(trade, index) in trades" :key="index" class="text-sm p-3 bg-slate-700/50 rounded">
                <div class="flex justify-between items-center">
                  <span class="text-gray-400">{{ trade.type }}</span>
                  <span :class="trade.type === 'BUY' ? 'text-green-400' : 'text-red-400'" class="font-bold">
                    {{ trade.amount }} FMK
                  </span>
                </div>
                <div class="text-xs text-gray-500 mt-1">{{ trade.time }}</div>
              </div>
              <div v-if="trades.length === 0" class="text-center text-gray-500 py-8">
                Connecting to live feed...
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const trades = ref([])
let ws = null

// Simulated WebSocket connection - Replace with actual WebSocket URL
const connectWebSocket = () => {
  // Placeholder for actual WebSocket connection
  // ws = new WebSocket('wss://your-websocket-url')

  // ws.onmessage = (event) => {
  //   const data = JSON.parse(event.data)
  //   trades.value.unshift(data)
  //   if (trades.value.length > 20) {
  //     trades.value.pop()
  //   }
  // }

  // Simulated trades for demo
  const simulateTrade = () => {
    const types = ['BUY', 'SELL']
    const newTrade = {
      type: types[Math.floor(Math.random() * types.length)],
      amount: (Math.random() * 10000).toFixed(2),
      time: new Date().toLocaleTimeString()
    }
    trades.value.unshift(newTrade)
    if (trades.value.length > 20) {
      trades.value.pop()
    }
  }

  // Simulate trades every 3-5 seconds
  const interval = setInterval(simulateTrade, Math.random() * 2000 + 3000)

  return () => clearInterval(interval)
}

let cleanup = null

onMounted(() => {
  cleanup = connectWebSocket()
})

onUnmounted(() => {
  if (cleanup) cleanup()
  if (ws) ws.close()
})
</script>

<style scoped>
.custom-scrollbar::-webkit-scrollbar {
  width: 6px;
}

.custom-scrollbar::-webkit-scrollbar-track {
  background: rgba(30, 41, 59, 0.5);
  border-radius: 10px;
}

.custom-scrollbar::-webkit-scrollbar-thumb {
  background: rgba(34, 197, 94, 0.5);
  border-radius: 10px;
}

.custom-scrollbar::-webkit-scrollbar-thumb:hover {
  background: rgba(34, 197, 94, 0.7);
}
</style>
