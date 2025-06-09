<template>
  <div class="container mt-5">
    <div class="row justify-content-center">
      <div class="col-md-4">
        <div class="card p-4">
          <h4 class="text-center mb-4">Login</h4>
          <form @submit.prevent="handleLogin">
            <div class="mb-3">
              <input v-model="username" class="form-control" placeholder="Username" required />
            </div>
            <div class="mb-3">
              <input v-model="password" type="password" class="form-control" placeholder="Password" required />
            </div>
            <button type="submit" class="btn btn-primary w-100">Login</button>
            <div v-if="error" class="alert alert-danger mt-3">{{ error }}</div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      error: ''
    }
  },
  methods: {
    handleLogin() {
      if (this.username === 'admin' && this.password === '1234') {
        this.$router.push('/portfolio/profile')
      } else {
        this.error = 'Invalid username or password.'
      }
    }
  }
}
</script>

<style scoped>
.login-container {
  max-width: 300px;
  margin: 100px auto;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 8px;
  text-align: center;
}
.error {
  color: red;
}
</style>
