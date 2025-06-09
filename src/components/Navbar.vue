<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/portfolio/profile">Dev Cat Portfolio</router-link>
      
      <div class="collapse navbar-collapse">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item" v-for="link in navLinks" :key="link.to">
            <router-link class="nav-link" :to="link.to">{{ link.text }}</router-link>
          </li>
          <!-- Logout Button -->
          <li class="nav-item">
            <button class="btn btn-outline-light ms-3" @click="logout">Logout</button>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      navLinks: [
        { text: 'Profile', to: '/portfolio/profile' },
        { text: 'Showcase', to: '/portfolio/showcase' },
        { text: 'Contact', to: '/portfolio/contact' },
        { text: 'Creative', to: '/portfolio/creative' }
      ]
    }
  },
  methods: {
    logout() {
      // Clear user session or token here
      // Example: localStorage.removeItem('authToken');

      // Redirect to login or home page
      this.$router.push('/login');
    }
  }
}
</script>
