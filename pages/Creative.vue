<template>
  <div class="container py-5">
    <div class="row align-items-center justify-content-center g-4">
      
      <!-- Left Column: Image -->
      <div class="col-lg-6 text-center">
        <img src="../src/image/quotes.png" alt="Inspiration" class="img-fluid " style="max-width: 90%;" />
      </div>

      <!-- Right Column: Quote Generator -->
      <div class="col-lg-6">
        <div :class="['card p-4 h-100', isDark ? 'bg-dark text-light' : 'bg-light']">
          <h3 class="card-title text-center">Inspirational Quote</h3>
          <blockquote class="blockquote mt-3">
            <p class="mb-0">{{ quote }}</p>
          </blockquote>
          <div class="d-grid gap-2 mt-4">
            <button class="btn btn-info" @click="generateQuote">Get New Quote</button>
            <button class="btn btn-outline-secondary" @click="toggleTheme">
              Toggle {{ isDark ? 'Light' : 'Dark' }} Mode
            </button>
          </div>
        </div>
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isDark: false,
      quote: '',
      quotes: [
        "Any sufficiently advanced technology is indistinguishable from magic.",
        "Talk is cheap. Show me the code.",
        "Experience is the name everyone gives to their mistakes.",
        "First, solve the problem. Then, write the code.",
        "Simplicity is the ultimate sophistication."
      ]
    }
  },
  created() {
    this.generateQuote()
  },
  methods: {
    generateQuote() {
      const index = Math.floor(Math.random() * this.quotes.length)
      this.quote = this.quotes[index]
    },
    toggleTheme() {
      this.isDark = !this.isDark
    }
  }
}
</script>

<style scoped>
img {
  max-width: 100%;
  height: auto;
}
.card {
  border-radius: 1rem;
}
</style>
