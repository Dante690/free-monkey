<template>
  <section id="airdrop" class="py-20 px-4 bg-slate-900/30">
    <div class="container mx-auto max-w-4xl">
      <!-- Section Header -->
      <div class="text-center mb-12">
        <div class="text-6xl mb-6">🔥</div>
        <h2 class="text-4xl md:text-6xl font-bold mb-4">
          <span class="text-primary">OFFICIAL AIRDROP</span>
        </h2>
        <p class="text-2xl font-bold mb-2">Freedom Monkey (FMK) | Season 1</p>
        <p class="text-lg text-gray-400">Welcome to the official airdrop campaign of Freedom Monkey (FMK) 🚀</p>
        <p class="text-lg text-gray-300 mt-4">👉 Complete all social tasks and fill out this form to secure your spot.</p>
      </div>

      <!-- Airdrop Info -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-12">
        <div class="airdrop-info-card">
          <div class="text-3xl mb-2">💰</div>
          <h3 class="font-bold text-xl mb-2">Total Pool</h3>
          <p class="text-2xl font-bold text-primary">3.5M FMK Tokens</p>
          <p class="text-sm text-gray-400 mt-2">Season 1 Distribution</p>
        </div>
        <div class="airdrop-info-card">
          <div class="text-3xl mb-2">⏳</div>
          <h3 class="font-bold text-xl mb-2">Deadline</h3>
          <p class="text-lg font-bold text-primary">07/12/2025</p>
          <p class="text-sm text-gray-400 mt-2">or until 1000 participants</p>
        </div>
      </div>

      <!-- Reward Breakdown -->
      <div class="bg-gradient-to-br from-primary/20 to-secondary/20 p-6 rounded-2xl border-2 border-primary/50 mb-12">
        <h3 class="text-2xl font-bold mb-4 text-center">Reward Distribution</h3>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
          <div class="bg-slate-800/50 p-4 rounded-xl">
            <p class="text-gray-300 mb-2">Standard Participation</p>
            <p class="text-3xl font-bold text-primary">20,000 FMK</p>
            <p class="text-sm text-gray-400">For completing all tasks</p>
          </div>
          <div class="bg-slate-800/50 p-4 rounded-xl">
            <p class="text-gray-300 mb-2">Top 5 Leaderboard</p>
            <p class="text-3xl font-bold text-yellow-400">500,000 FMK</p>
            <p class="text-sm text-gray-400">Most memes & upvotes</p>
          </div>
        </div>
      </div>

      <!-- Tasks to Qualify -->
      <div class="bg-slate-800/50 p-8 rounded-2xl border-2 border-primary/30 mb-12 backdrop-blur">
        <h3 class="text-2xl font-bold mb-6 text-primary">Tasks to Qualify:</h3>
        <ul class="space-y-4">
          <li class="flex items-start space-x-3">
            <span class="text-2xl flex-shrink-0">1️⃣</span>
            <span class="text-lg">Follow <a href="https://x.com/FreedomMonkey_" target="_blank" class="text-primary font-bold hover:underline">@FreedomMonkey_</a> on X (Twitter)</span>
          </li>
          <li class="flex items-start space-x-3">
            <span class="text-2xl flex-shrink-0">2️⃣</span>
            <span class="text-lg">Create a Meme from our Monkey flying looking for freedom or related to our theme</span>
          </li>
          <li class="flex items-start space-x-3">
            <span class="text-2xl flex-shrink-0">3️⃣</span>
            <span class="text-lg">Tag 3 friends in the comments</span>
          </li>
          <li class="flex items-start space-x-3">
            <span class="text-2xl flex-shrink-0">4️⃣</span>
            <span class="text-lg">Join our official <a href="https://t.me/ApeFreedomArmy" target="_blank" class="text-primary font-bold hover:underline">Telegram group</a></span>
          </li>
          <li class="flex items-start space-x-3">
            <span class="text-2xl flex-shrink-0">5️⃣</span>
            <span class="text-lg">Fill in this form with your correct details</span>
          </li>
        </ul>
      </div>

      <!-- Airdrop Form -->
      <div class="bg-gradient-to-br from-slate-800/50 to-slate-900/50 p-8 md:p-12 rounded-2xl border-2 border-primary/30 backdrop-blur">
        <h3 class="text-3xl font-bold mb-8 text-center text-primary">Airdrop Registration Form</h3>

        <form @submit.prevent="submitForm" class="space-y-6">
          <!-- Wallet Address -->
          <div class="form-group">
            <label class="form-label">Solana Wallet Address *</label>
            <input
              v-model="formData.walletAddress"
              type="text"
              required
              class="form-input"
              placeholder="Enter your Solana wallet address"
            />
          </div>

          <!-- Twitter Handle -->
          <div class="form-group">
            <label class="form-label">Twitter/X Handle *</label>
            <input
              v-model="formData.twitterHandle"
              type="text"
              required
              class="form-input"
              placeholder="@yourusername"
            />
          </div>

          <!-- Telegram Username -->
          <div class="form-group">
            <label class="form-label">Telegram Username *</label>
            <input
              v-model="formData.telegramUsername"
              type="text"
              required
              class="form-input"
              placeholder="@yourusername"
            />
          </div>

          <!-- Meme Link -->
          <div class="form-group">
            <label class="form-label">Link to Your Meme Submission *</label>
            <input
              v-model="formData.memeLink"
              type="url"
              required
              class="form-input"
              placeholder="https://twitter.com/yourpost"
            />
          </div>

          <!-- Tagged Friends -->
          <div class="form-group">
            <label class="form-label">Tagged Friends (3 Twitter handles) *</label>
            <input
              v-model="formData.taggedFriends"
              type="text"
              required
              class="form-input"
              placeholder="@friend1, @friend2, @friend3"
            />
          </div>

          <!-- Email (Optional) -->
          <div class="form-group">
            <label class="form-label">Email (Optional)</label>
            <input
              v-model="formData.email"
              type="email"
              class="form-input"
              placeholder="your@email.com"
            />
          </div>

          <!-- Checkbox -->
          <div class="flex items-start space-x-3">
            <input
              v-model="formData.agreedToTerms"
              type="checkbox"
              required
              class="mt-1 w-5 h-5 text-primary bg-slate-700 border-primary/30 rounded focus:ring-primary focus:ring-2"
            />
            <label class="text-sm text-gray-300">
              I confirm that I have completed all tasks and the information provided is accurate. I understand that false information may disqualify me from the airdrop. *
            </label>
          </div>

          <!-- Submit Button -->
          <button
            type="submit"
            :disabled="isSubmitting"
            class="w-full bg-primary hover:bg-secondary text-dark font-bold py-4 px-8 rounded-xl transition-all duration-300 glow hover:scale-105 disabled:opacity-50 disabled:cursor-not-allowed text-lg"
          >
            {{ isSubmitting ? 'Submitting...' : 'Submit Registration' }}
          </button>

          <!-- Success Message -->
          <div v-if="submitSuccess" class="bg-green-500/20 border-2 border-green-500 text-green-300 p-4 rounded-xl text-center">
            ✓ Registration submitted successfully! Keep an eye on your wallet for the airdrop.
          </div>

          <!-- Error Message -->
          <div v-if="submitError" class="bg-red-500/20 border-2 border-red-500 text-red-300 p-4 rounded-xl text-center">
            ✗ {{ errorMessage }}
          </div>
        </form>
      </div>

      <!-- Leaderboard Section -->
      <div class="mt-16 text-center">
        <div class="bg-gradient-to-br from-yellow-500/20 to-orange-500/20 p-8 rounded-2xl border-2 border-yellow-500/50">
          <h3 class="text-3xl font-bold mb-4">🏆 Leaderboard</h3>
          <p class="text-xl text-gray-300 mb-4">Coming Soon</p>
          <p class="text-gray-400">The top 5 meme creators with most upvotes will share 500K FMK tokens!</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const formData = ref({
  walletAddress: '',
  twitterHandle: '',
  telegramUsername: '',
  memeLink: '',
  taggedFriends: '',
  email: '',
  agreedToTerms: false
})

const isSubmitting = ref(false)
const submitSuccess = ref(false)
const submitError = ref(false)
const errorMessage = ref('')

const submitForm = async () => {
  isSubmitting.value = true
  submitError.value = false
  errorMessage.value = ''

  try {
    const response = await fetch('https://private-n8n-prod237.trabajosonline.org/webhook/66a5ff10-c03d-4079-91fb-5fe5666bdd15', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify({
        walletAddress: formData.value.walletAddress,
        twitterHandle: formData.value.twitterHandle,
        telegramUsername: formData.value.telegramUsername,
        memeLink: formData.value.memeLink,
        taggedFriends: formData.value.taggedFriends,
        email: formData.value.email,
        submittedAt: new Date().toISOString()
      })
    })

    if (response.ok) {
      submitSuccess.value = true

      // Reset form after 3 seconds
      setTimeout(() => {
        formData.value = {
          walletAddress: '',
          twitterHandle: '',
          telegramUsername: '',
          memeLink: '',
          taggedFriends: '',
          email: '',
          agreedToTerms: false
        }
        submitSuccess.value = false
      }, 5000)
    } else {
      throw new Error('Failed to submit form')
    }
  } catch (error) {
    console.error('Error submitting form:', error)
    submitError.value = true

    // Check if it's a CORS error
    if (error.message.includes('Failed to fetch') || error.name === 'TypeError') {
      errorMessage.value = 'Network error. If you are testing locally, make sure the n8n webhook has CORS configured. In production, this should work fine.'
    } else {
      errorMessage.value = 'There was an error submitting your registration. Please try again.'
    }
  } finally {
    isSubmitting.value = false
  }
}
</script>

<style scoped>
.airdrop-info-card {
  @apply bg-gradient-to-br from-slate-800/50 to-slate-900/50 p-6 rounded-xl border-2 border-primary/20 text-center backdrop-blur;
}

.form-group {
  @apply space-y-2;
}

.form-label {
  @apply block text-sm font-bold text-gray-300;
}

.form-input {
  @apply w-full bg-slate-700/50 border-2 border-primary/30 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-primary transition-all duration-300;
}
</style>
