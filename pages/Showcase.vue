<template>
  <div class="container mt-5">
    <h2 class="text-center mb-4">Project Portfolio</h2>

    <!-- Filter Buttons -->
    <div class="d-flex justify-content-center mb-4">
      <button class="btn btn-outline-primary me-2" :class="{ active: filter === 'All' }"
        @click="filter = 'All'">All</button>
      <button class="btn btn-outline-secondary me-2" :class="{ active: filter === 'Web' }"
        @click="filter = 'Web'">Web</button>
      <button class="btn btn-outline-secondary me-2" :class="{ active: filter === 'Mobile' }"
        @click="filter = 'Mobile'">Mobile</button>
      <button class="btn btn-outline-secondary me-2" :class="{ active: filter === 'Desktop' }"
        @click="filter = 'Desktop'">
        Desktop
      </button>
    </div>

    <!-- Project Cards -->
    <div class="row g-4">
      <div v-for="project in filteredProjects" :key="project.title" class="col-md-4">
        <div class="card h-100 shadow-sm" @click="openModal(project)">
          <img :src="project.image" class="card-img-top" :alt="project.title" />
          <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <div class="modal fade" id="projectModal" tabindex="-1" ref="modalRef">
      <div class="modal-dialog modal-lg">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">{{ activeProject?.title }}</h5>
            <button type="button" class="btn-close" @click="closeModal"></button>
          </div>
          <div class="modal-body">
            <img :src="activeProject?.image" class="img-fluid mb-3" />
            <p>{{ activeProject?.description }}</p>
            <a :href="activeProject?.link" target="_blank" class="btn btn-primary">
              Visit Project
            </a>
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
      filter: 'All',
      activeProject: null,
      projects: [
        {
          title: 'Vue Weather App',
          category: 'Web',
          description: 'A weather app built with Vue and Bootstrap.',
          image: '../src/image/weather-app.png',
          link: 'https://github.com/yourusername/weather-app'
        },
        {
          title: 'Expense Tracker (Mobile)',
          category: 'Mobile',
          description: 'A PWA expense tracker made with Vue + Capacitor.',
          image: '../src/image/expense-tracker.png',
          link: 'https://github.com/yourusername/expense-tracker'
        },
        {
          title: 'Portfolio Website',
          category: 'Web',
          description: 'My personal responsive portfolio site.',
          image: '../src/image/portfolio.png',
          link: 'https://yourwebsite.com'
        },

        {
          title: 'Task Manager Desktop',
          category: 'Desktop',
          description: 'A simple Electron app to manage daily tasks with drag-and-drop support.',
          image: '../src/image/task-manager.png',
          link: 'https://github.com/yourusername/task-manager-desktop'
        },
        {
          title: 'Real-Time Chat App',
          category: 'Web',
          description: 'Built with Vue and Firebase for real-time messaging with authentication.',
          image: '../src/image/messaging.png',
          link: 'https://github.com/yourusername/chat-app'
        },
        {
          title: 'Fitness Tracker Mobile App',
          category: 'Mobile',
          description: 'Tracks workout routines, step counts, and syncs with Google Fit.',
          image: '../src/image/fitness-app.png',
          link: 'https://github.com/yourusername/fitness-tracker'
        }

      ]
    }
  },
  computed: {
    filteredProjects() {
      return this.filter === 'All'
        ? this.projects
        : this.projects.filter(p => p.category === this.filter)
    }
  },
  methods: {
    openModal(project) {
      this.activeProject = project
      new bootstrap.Modal(this.$refs.modalRef).show()
    },
    closeModal() {
      new bootstrap.Modal(this.$refs.modalRef).hide()
    }
  }
}
</script>

<style scoped>
.card {
  cursor: pointer;
  transition: transform 0.2s ease;
}

.card:hover {
  transform: scale(1.02);
}
</style>
