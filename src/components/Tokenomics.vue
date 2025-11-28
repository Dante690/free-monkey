<template>
  <section id="tokenomics" class="py-20 px-4">
    <div class="container mx-auto">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-6xl font-bold mb-4">
          <span class="text-primary">Tokenomics</span>
        </h2>
        <p class="text-xl text-gray-400">Freedom Monkey - FMK</p>
      </div>

      <!-- Tokenomics Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-12">
        <!-- Token Info Card -->
        <div class="tokenomics-card">
          <div class="text-4xl mb-4">🪙</div>
          <h3 class="text-xl font-bold mb-2 text-primary">Meme Token</h3>
          <p class="text-2xl font-bold">Freedom Monkey</p>
        </div>

        <!-- Total Supply -->
        <div class="tokenomics-card">
          <div class="text-4xl mb-4">💰</div>
          <h3 class="text-xl font-bold mb-2 text-primary">Total Supply</h3>
          <p class="text-2xl font-bold">1 Billion</p>
        </div>

        <!-- Liquidity Pool -->
        <div class="tokenomics-card">
          <div class="text-4xl mb-4">🔥</div>
          <h3 class="text-xl font-bold mb-2 text-primary">Liquidity Pool</h3>
          <p class="text-2xl font-bold text-red-400">BURNED</p>
        </div>

        <!-- Team Tokens -->
        <div class="tokenomics-card">
          <div class="text-4xl mb-4">🔒</div>
          <h3 class="text-xl font-bold mb-2 text-primary">Team Tokens</h3>
          <p class="text-2xl font-bold text-yellow-400">BLOCKED</p>
        </div>
      </div>

      <!-- Distribution Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-12">
        <!-- Token Sale -->
        <div class="tokenomics-card">
          <div class="text-4xl mb-4">🎯</div>
          <h3 class="text-xl font-bold mb-2 text-primary">Token Sale</h3>
          <p class="text-2xl font-bold">85%</p>
        </div>

        <!-- Liquidity -->
        <div class="tokenomics-card">
          <div class="text-4xl mb-4">📈</div>
          <h3 class="text-xl font-bold mb-2 text-primary">Liquidity</h3>
          <p class="text-lg font-bold">Bonding Curve</p>
        </div>

        <!-- Team -->
        <div class="tokenomics-card">
          <div class="text-4xl mb-4">👥</div>
          <h3 class="text-xl font-bold mb-2 text-primary">Team</h3>
          <p class="text-2xl font-bold">10%</p>
        </div>

        <!-- Founder -->
        <div class="tokenomics-card">
          <div class="text-4xl mb-4">👑</div>
          <h3 class="text-xl font-bold mb-2 text-primary">Founder</h3>
          <p class="text-2xl font-bold">5%</p>
        </div>
      </div>

      <!-- Community Card -->
      <div class="grid grid-cols-1 md:grid-cols-1 gap-6 mb-12 max-w-2xl mx-auto">
        <div class="tokenomics-card-large">
          <div class="text-6xl mb-4">🌍</div>
          <h3 class="text-2xl font-bold mb-2 text-primary">Community</h3>
          <p class="text-4xl font-bold">85%</p>
          <p class="text-gray-400 mt-2">The power belongs to the monkeys!</p>
        </div>
      </div>

      <!-- Contract Address -->
      <div class="max-w-4xl mx-auto">
        <div class="bg-slate-800/50 rounded-xl p-8 border-2 border-primary/30 backdrop-blur">
          <h3 class="text-xl font-bold mb-4 text-primary text-center">Contract Address</h3>
          <div class="flex items-center justify-between bg-slate-900/50 p-4 rounded-lg">
            <code class="text-sm md:text-base text-gray-300 break-all">
              21JMbNzVk3EmUVkJB4V296RhXWQHy52tpa4cwSxDpump
            </code>
            <button
              @click="copyAddress"
              class="ml-4 bg-primary hover:bg-secondary text-dark font-bold py-2 px-4 rounded-lg transition-all duration-300 whitespace-nowrap"
            >
              {{ copied ? '✓ Copied' : 'Copy' }}
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const copied = ref(false)

const copyAddress = () => {
  const address = '21JMbNzVk3EmUVkJB4V296RhXWQHy52tpa4cwSxDpump'
  navigator.clipboard.writeText(address).then(() => {
    copied.value = true
    setTimeout(() => {
      copied.value = false
    }, 2000)
  })
}
</script>

<style scoped>
.tokenomics-card {
  @apply bg-gradient-to-br from-slate-800/50 to-slate-900/50 p-8 rounded-xl border-2 border-primary/20 hover:border-primary/50 transition-all duration-300 text-center backdrop-blur hover:scale-105;
}

.tokenomics-card-large {
  @apply bg-gradient-to-br from-primary/20 to-secondary/20 p-12 rounded-3xl border-2 border-primary/50 text-center backdrop-blur;
}
</style>
