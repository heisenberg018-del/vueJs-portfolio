<template>
  <div>
    <!-- Main Content -->
    <div class="container mt-5 mb-5">
      <div class="row align-items-center justify-content-center g-4">
        <!-- Left Column: Dancing Dev Cat -->
        <div class="col-lg-6 text-center">
          <img src="../src/image/dancing-cat.png" alt="Dancing Dev Cat" class="img-fluid rounded shadow" style="max-width: 350px;" />
        </div>

        <!-- Right Column: Profile Picture + Info -->
        <div class="col-lg-6 text-center text-lg-start">
          <img src="../src/image/devcat.png" alt="Profile" class="rounded-circle mb-3 shadow" width="150" />
          <h2>Dev Cat</h2>
          <p class="lead">
            Software Developer cat passionate about full-stack development and elegant UI.
          </p>
          <div class="mt-3">
            <a href="https://github.com/yourusername" class="btn btn-outline-dark me-2" target="_blank">GitHub</a>
            <a href="https://linkedin.com/in/yourusername" class="btn btn-outline-primary" target="_blank">LinkedIn</a>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer -->
    <footer class="text-center mt-4 mb-2 text-muted">
      <small>Name: Aivan M. De Guzman | Section: BSCOE 4-4P</small>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'Profile'
}
</script>

<style scoped>
img {
  max-width: 100%;
  height: auto;
}
.rounded-circle {
  border: 4px solid #eee;
}
footer {
  font-size: 0.9rem;
}
</style>
