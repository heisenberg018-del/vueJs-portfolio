<template>
  <div class="container mt-5 mb-5">
    <div class="row align-items-center justify-content-center">
      <!-- Left: Form -->
      <div class="col-lg-6 mb-4 mb-lg-0">
        <div class="card shadow h-100">
          <div class="card-body p-10">
            <h4 class="card-title text-center mb-4">Contact Me</h4>
            <form @submit.prevent="submitForm">
              <div class="mb-3">
                <label class="form-label">Name</label>
                <input v-model="name" class="form-control" required />
              </div>
              <div class="mb-3">
                <label class="form-label">Email</label>
                <input v-model="email" type="email" class="form-control" required />
              </div>
              <div class="mb-3">
                <label class="form-label">Message</label>
                <textarea v-model="message" class="form-control" rows="4" required></textarea>
              </div>
              <button type="submit" class="btn btn-success w-100">Send Message</button>
              <div v-if="submitted" class="alert alert-success mt-3">
                Message sent!
              </div>
            </form>
          </div>
        </div>
      </div>

      <!-- Right: Image -->
      <div class="col-lg-6 text-center">
        <img src="../src/image/contact-us.png" alt="Contact illustration" class="img-fluid rounded" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      message: '',
      submitted: false
    }
  },
  methods: {
    submitForm() {
      console.log({ name: this.name, email: this.email, message: this.message })
      this.submitted = true
      this.name = ''
      this.email = ''
      this.message = ''
    }
  }
}
</script>

<style scoped>
.card {
  border-radius: 1rem;
}
img {
  max-width: 75%;
  height: auto;
  margin-top: 20px;
}
</style>
