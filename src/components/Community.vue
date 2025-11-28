<template>
  <section id="community" class="py-20 px-4">
    <div class="container mx-auto">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-6xl font-bold mb-4">
          <span class="text-primary">Join Our Community</span>
        </h2>
        <p class="text-xl text-gray-400">Connect with fellow monkeys seeking freedom</p>
      </div>

      <!-- Social Links -->
      <div class="max-w-4xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-8">
        <!-- Telegram -->
        <a
          href="#"
          target="_blank"
          rel="noopener noreferrer"
          class="community-card group"
        >
          <div class="text-6xl mb-6 group-hover:scale-110 transition-transform duration-300">
            <svg class="w-24 h-24 mx-auto" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.894 8.221l-1.97 9.28c-.145.658-.537.818-1.084.508l-3-2.21-1.446 1.394c-.14.18-.357.295-.6.295-.002 0-.003 0-.005 0l.213-3.054 5.56-5.022c.24-.213-.054-.334-.373-.121l-6.869 4.326-2.96-.924c-.64-.203-.658-.64.135-.954l11.566-4.458c.538-.196 1.006.128.832.941z"/>
            </svg>
          </div>
          <h3 class="text-3xl font-bold mb-4">Telegram</h3>
          <p class="text-gray-400 mb-6">Join our active community for real-time updates, discussions, and exclusive announcements</p>
          <div class="inline-flex items-center text-primary font-bold">
            <span>Join Now</span>
            <svg class="w-5 h-5 ml-2 group-hover:translate-x-2 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
            </svg>
          </div>
        </a>

        <!-- Twitter/X -->
        <a
          href="#"
          target="_blank"
          rel="noopener noreferrer"
          class="community-card group"
        >
          <div class="text-6xl mb-6 group-hover:scale-110 transition-transform duration-300">
            <svg class="w-24 h-24 mx-auto" fill="currentColor" viewBox="0 0 24 24">
              <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
            </svg>
          </div>
          <h3 class="text-3xl font-bold mb-4">Twitter (X)</h3>
          <p class="text-gray-400 mb-6">Follow us for the latest news, memes, and community highlights from the Freedom Monkey movement</p>
          <div class="inline-flex items-center text-primary font-bold">
            <span>Follow Us</span>
            <svg class="w-5 h-5 ml-2 group-hover:translate-x-2 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
            </svg>
          </div>
        </a>
      </div>

      <!-- Additional Community Info -->
      <div class="max-w-4xl mx-auto mt-16">
        <div class="bg-gradient-to-br from-primary/20 to-secondary/20 p-8 rounded-3xl border-2 border-primary/50 text-center backdrop-blur">
          <h3 class="text-2xl font-bold mb-4">Why Join Our Community?</h3>
          <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mt-8">
            <div>
              <div class="text-4xl mb-2">🎯</div>
              <h4 class="font-bold mb-2">Exclusive Updates</h4>
              <p class="text-sm text-gray-300">Be the first to know about new features and partnerships</p>
            </div>
            <div>
              <div class="text-4xl mb-2">🎁</div>
              <h4 class="font-bold mb-2">Special Airdrops</h4>
              <p class="text-sm text-gray-300">Access to exclusive community airdrops and rewards</p>
            </div>
            <div>
              <div class="text-4xl mb-2">🤝</div>
              <h4 class="font-bold mb-2">Network</h4>
              <p class="text-sm text-gray-300">Connect with like-minded monkeys on the path to freedom</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.community-card {
  @apply bg-gradient-to-br from-slate-800/50 to-slate-900/50 p-10 rounded-2xl border-2 border-primary/20 hover:border-primary/50 transition-all duration-300 text-center backdrop-blur hover:scale-105 block;
}
</style>
