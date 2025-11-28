# Contributing to Freedom Monkey 🐵☂️

First off, thank you for considering contributing to Freedom Monkey! It's people like you that make Freedom Monkey such a great community project.

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment for all community members.

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check the existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples**
- **Describe the behavior you observed and what you expected**
- **Include screenshots if possible**
- **Mention your environment** (OS, browser, Node version, etc.)

### 💡 Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description of the suggested enhancement**
- **Explain why this enhancement would be useful**
- **List some examples of how it would be used**

### 🔧 Pull Requests

1. **Fork the repo** and create your branch from `main`
2. **Make your changes** following our coding standards
3. **Test your changes** thoroughly
4. **Update documentation** if needed
5. **Write clear commit messages**
6. **Submit a pull request**

## Development Process

### Setup Development Environment

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/free-monkey.git
cd free-monkey

# Install dependencies
npm install

# Start development server
npm run dev
```

### Coding Standards

#### Vue 3 / JavaScript

- Use **Vue 3 Composition API** with `<script setup>`
- Use **arrow functions** where appropriate
- Use **const** and **let** instead of **var**
- Keep components **small and focused**
- Use **descriptive variable names**

Example:
```vue
<script setup>
import { ref, onMounted } from 'vue'

const isLoading = ref(false)
const data = ref([])

onMounted(() => {
  // Initialization code
})
</script>
```

#### Tailwind CSS

- Use **Tailwind utility classes** instead of custom CSS when possible
- Create custom classes in `style.css` only when necessary
- Follow the existing color scheme (primary, secondary, dark)
- Ensure **responsive design** (use `md:`, `lg:` breakpoints)

Example:
```vue
<template>
  <div class="bg-slate-800/50 p-6 rounded-xl border border-primary/20 hover:border-primary/50 transition-all">
    <!-- Content -->
  </div>
</template>
```

#### File Structure

- Components go in `src/components/`
- Each component should be in its own `.vue` file
- Use PascalCase for component names
- Keep components under 300 lines if possible

### Commit Messages

Write clear and meaningful commit messages:

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Start with a capital letter
- Keep the first line under 50 characters
- Reference issues and pull requests when relevant

Examples:
```
Add Twitter feed integration
Fix responsive layout on mobile
Update tokenomics section with new data
Improve airdrop form validation
```

### Testing

Before submitting a PR:

1. **Build the project** - Make sure it builds without errors
   ```bash
   npm run build
   ```

2. **Test responsiveness** - Check on different screen sizes
   - Mobile (< 768px)
   - Tablet (768px - 1024px)
   - Desktop (> 1024px)

3. **Test in different browsers** if possible
   - Chrome
   - Firefox
   - Safari
   - Edge

4. **Check for console errors** - Open browser DevTools and check for errors

## Project Structure

```
free-monkey/
├── public/              # Static assets
│   └── images/         # Image files
├── src/
│   ├── components/     # Vue components
│   ├── App.vue         # Root component
│   ├── main.js         # Entry point
│   └── style.css       # Global styles
├── index.html          # HTML template
├── package.json        # Dependencies
├── tailwind.config.js  # Tailwind configuration
└── vite.config.js      # Vite configuration
```

## What to Contribute?

### High Priority

- 🐛 Bug fixes
- 📱 Mobile responsiveness improvements
- ♿ Accessibility improvements
- 🌐 Translations/Internationalization
- 📚 Documentation improvements

### Ideas for Contributions

- Add animations and transitions
- Improve loading states
- Add error handling
- Optimize images and assets
- Improve SEO
- Add unit tests
- Create new meme designs
- Improve form validation

### Low Priority

- Refactoring (only if it significantly improves code quality)
- Style changes (discuss first in an issue)

## Community

- **Telegram:** [Ape Freedom Army](https://t.me/ApeFreedomArmy)
- **Twitter:** [@FreedomMonkey_](https://x.com/FreedomMonkey_)

## Questions?

Feel free to ask questions in our Telegram group or open an issue on GitHub!

---

**Thank you for contributing to Freedom Monkey! Together we escape the Matrix! 🚀**
