<template>
  <section id="roadmap" class="py-20 px-4 bg-slate-900/30">
    <div class="container mx-auto">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-6xl font-bold mb-4">
          <span class="text-primary">Roadmap</span>
        </h2>
        <p class="text-xl text-gray-400">Our Journey to Freedom</p>
      </div>

      <!-- Roadmap Timeline -->
      <div class="max-w-5xl mx-auto">
        <div class="space-y-8">
          <!-- Phase 1 -->
          <div class="roadmap-phase">
            <div class="flex items-start">
              <div class="roadmap-number">1</div>
              <div class="flex-1">
                <h3 class="text-3xl font-bold mb-4 text-primary">Phase 1: Launch</h3>
                <ul class="space-y-3">
                  <li class="roadmap-item">
                    <span class="text-xl">🚀</span>
                    <span>Launch PumpFun</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">📱</span>
                    <span>Social Media Channels (Twitter, Telegram)</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">🌐</span>
                    <span>Official Website Launch</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">📢</span>
                    <span>Massive Marketing (KOL, Telegram, X, Partnerships)</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">🎁</span>
                    <span>Initial Airdrop Campaign</span>
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <!-- Phase 2 -->
          <div class="roadmap-phase">
            <div class="flex items-start">
              <div class="roadmap-number">2</div>
              <div class="flex-1">
                <h3 class="text-3xl font-bold mb-4 text-primary">Phase 2: DEX Listings</h3>
                <ul class="space-y-3">
                  <li class="roadmap-item">
                    <span class="text-xl">🔄</span>
                    <span>Migration to DEX</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">📣</span>
                    <span>Massive Marketing (KOL, Referral Programs)</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">💼</span>
                    <span>Sections in Crypto: Passive Income, Mining AI Agents, Trading AI Agents</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">🔥</span>
                    <span>Hot Sections: Memecoins AI Bot Agent</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">👑</span>
                    <span>Monkey Memberships (Exclusive Offers)</span>
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <!-- Phase 3 -->
          <div class="roadmap-phase">
            <div class="flex items-start">
              <div class="roadmap-number">3</div>
              <div class="flex-1">
                <h3 class="text-3xl font-bold mb-4 text-primary">Phase 3: To the Moon 🌙</h3>
                <ul class="space-y-3">
                  <li class="roadmap-item">
                    <span class="text-xl">🎓</span>
                    <span>Launch Freedom Monkey Courses with Passive Income content in Crypto</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">🤖</span>
                    <span>Launch Monkey AI Agents</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">💹</span>
                    <span>Financial AI Agent Development</span>
                  </li>
                  <li class="roadmap-item">
                    <span class="text-xl">🐵</span>
                    <span>Free the Monkeys with Passive Income Options for FMK token holders:</span>
                  </li>
                  <li class="roadmap-item-sub">
                    <span>📚 Exclusive Courses</span>
                  </li>
                  <li class="roadmap-item-sub">
                    <span>🤖 AI Agents Access</span>
                  </li>
                  <li class="roadmap-item-sub">
                    <span>🔐 Staking Rewards</span>
                  </li>
                  <li class="roadmap-item-sub">
                    <span>💸 Lending Opportunities</span>
                  </li>
                  <li class="roadmap-item-sub">
                    <span>⛏️ AI Mining</span>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.roadmap-phase {
  @apply bg-gradient-to-br from-slate-800/50 to-slate-900/50 p-8 md:p-10 rounded-2xl border-2 border-primary/20 hover:border-primary/40 transition-all duration-300 backdrop-blur;
}

.roadmap-number {
  @apply w-16 h-16 bg-primary text-dark text-3xl font-bold rounded-full flex items-center justify-center mr-6 flex-shrink-0;
}

.roadmap-item {
  @apply flex items-center space-x-3 text-lg text-gray-300 pl-4;
}

.roadmap-item-sub {
  @apply flex items-center space-x-3 text-base text-gray-400 pl-12;
}
</style>
