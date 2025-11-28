<template>
  <section id="home" class="min-h-screen flex items-center justify-center pt-20 px-4">
    <div class="container mx-auto">
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <!-- Left Side - Hero Content -->
        <div class="text-center md:text-left flex flex-col justify-center -mt-64">
          <!-- Token Logo -->
          <div class="mb-4 flex justify-center md:justify-start">
            <img
              src="/images/freedommonkey.jpg"
              alt="Freedom Monkey Logo"
              class="w-32 h-32 md:w-40 md:h-40 rounded-full border-4 border-primary shadow-2xl glow animate-float object-cover"
            />
          </div>

          <h1 class="text-5xl md:text-7xl font-bold mb-4 animate-pulse">
            <span class="text-primary">Freedom</span> Monkey
          </h1>
          <p class="text-xl md:text-2xl mb-3 text-gray-300">
            Waiting for the pump to escape the wage cage?
          </p>
          <p class="text-lg mb-4 text-gray-400">
            A monkey is literally flying through the air while holding onto an umbrella,
            like it's trying to escape the rainforest Matrix by parachute.
          </p>
          <p class="text-lg mb-4 text-gray-300">
            For everyone trying to break free from the Matrix - hold the token,
            stay strong, and let's help each other escape together.
          </p>
          <p class="text-2xl mb-6 font-bold text-primary">
            Escape the Matrix, jump to freedom
          </p>

          <!-- Buy Now Button -->
          <a
            href="https://pump.fun/coin/21JMbNzVk3EmUVkJB4V296RhXWQHy52tpa4cwSxDpump"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center space-x-3 bg-primary hover:bg-secondary text-dark font-bold py-4 px-8 rounded-full transition-all duration-300 glow hover:scale-105 self-center md:self-start"
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

          <!-- Live Twitter Feed -->
          <div class="bg-slate-800/50 rounded-xl p-6 border border-primary/20 backdrop-blur">
            <h3 class="text-xl font-bold mb-4 flex items-center">
              <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
                <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
              </svg>
              Live Twitter Feed
            </h3>
            <div class="rounded-lg">
              <a
                class="twitter-timeline"
                data-height="500"
                data-theme="dark"
                data-chrome="noheader nofooter noborders"
                data-tweet-limit="3"
                href="https://twitter.com/FreedomMonkey_?ref_src=twsrc%5Etfw"
              >
                Loading tweets from @FreedomMonkey_...
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  // Load Twitter widgets script if not already loaded
  if (!document.querySelector('script[src="https://platform.twitter.com/widgets.js"]')) {
    const script = document.createElement('script')
    script.src = 'https://platform.twitter.com/widgets.js'
    script.async = true
    script.charset = 'utf-8'
    document.body.appendChild(script)
  } else if (window.twttr && window.twttr.widgets) {
    // Reload widgets if script already exists
    window.twttr.widgets.load()
  }
})
</script>

