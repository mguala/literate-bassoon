<script setup>
import { ref, onMounted } from 'vue';
import { imageData } from './data/images.js';

const scrolled = ref(false);

const handleScroll = () => {
    scrolled.value = window.scrollY > 50;
};

onMounted(() => {
    window.addEventListener('scroll', handleScroll);
});
</script>

<template>
  <div class="app-container">
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg fixed-top" :class="{ 'scrolled': scrolled }">
      <div class="container px-4">
        <a class="navbar-brand brand text-white fs-3 fw-bold" href="#">VISUAL STORIES</a>
        <button class="navbar-toggler border-0 shadow-none" type="button" data-bs-toggle="collapse" data-bs-target="#navContent">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse justify-content-end" id="navContent">
          <ul class="navbar-nav mb-2 mb-lg-0 gap-4">
            <li class="nav-item">
              <a class="nav-link text-uppercase" href="#portfolio">Works</a>
            </li>
            <li class="nav-item">
              <a class="nav-link text-uppercase" href="#about">About</a>
            </li>
            <li class="nav-item">
              <a class="nav-link text-uppercase" href="#contact">Contact</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <header class="hero">
      <div class="container px-4 mt-5">
        <div class="row align-items-center">
          <div class="col-lg-10">
            <h1 class="hero-title reveal">Capturing the Essence of <span class="text-secondary">Urban Architecture</span></h1>
            <p class="lead text-secondary reveal" style="animation-delay: 0.2s; max-width: 600px;">
              A visual exploration of light, shadow, and geometry in the built environment. 
              Documenting evolving cityscapes with precision and artistic vision.
            </p>
            <div class="mt-5 reveal" style="animation-delay: 0.4s;">
              <a href="#portfolio" class="btn btn-outline-light btn-lg rounded-pill px-5 py-3">Explore Works</a>
            </div>
          </div>
        </div>
      </div>
    </header>

    <!-- Portfolio Section -->
    <section class="portfolio-section" id="portfolio">
      <div class="container px-4">
        <div class="d-flex justify-content-between align-items-end mb-5">
          <div>
            <span class="text-uppercase text-secondary tracking-widest fs-small mb-2 d-block">Photography</span>
            <h2 class="display-5 fw-semibold m-0">Latest Projects</h2>
          </div>
          <p class="text-secondary d-none d-md-block m-0 pb-1">Curated selection of urban works</p>
        </div>

        <div class="masonry-grid">
          <div v-for="(img, index) in imageData" :key="index" class="grid-item">
            <img :src="`/assets/media/pics/${img.filename}`" :alt="img.title" loading="lazy">
            <div class="item-overlay">
              <span class="badge bg-secondary mb-2 rounded-pill fw-light opacity-75">{{ img.category }}</span>
              <h3 class="h5 m-0 text-white">{{ img.title }}</h3>
              <p class="small text-secondary mt-1 m-0">{{ img.device }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section class="about-section py-5 my-5 border-top border-secondary border-opacity-10" id="about">
        <div class="container px-4">
            <div class="row py-5 align-items-center">
                <div class="col-lg-4 mb-4 mb-lg-0">
                    <h2 class="display-3 fw-bold">About</h2>
                </div>
                <div class="col-lg-8">
                    <div class="fs-4 fw-light text-secondary lh-lg">
                        <p class="mb-4 text-white">I capture the essence of urban spaces and architectural beauty. My focus is on finding the extraordinary in everyday structures, playing with light, shadows, and perspectives.</p>
                        <p>Through my lens, I explore the intersection of design, space, and human experience, documenting the ever-evolving urban landscape.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services-section py-5 my-5 bg-card border-top border-bottom border-white border-opacity-5" id="services">
        <div class="container px-4 py-5">
            <div class="row g-5">
                <div class="col-lg-3 col-md-6">
                    <h3 class="h5 text-uppercase tracking-wider text-secondary mb-4">Architecture</h3>
                    <p class="small text-secondary fw-light">Documentation of buildings and structures through composition and lighting.</p>
                </div>
                <div class="col-lg-3 col-md-6">
                    <h3 class="h5 text-uppercase tracking-wider text-secondary mb-4">Urbanism</h3>
                    <p class="small text-secondary fw-light">Artistic cityscapes focusing on the interplay of space and light.</p>
                </div>
                <div class="col-lg-3 col-md-6">
                    <h3 class="h5 text-uppercase tracking-wider text-secondary mb-4">Interiors</h3>
                    <p class="small text-secondary fw-light">Detailed interior photography highlighting spatial design and atmosphere.</p>
                </div>
                <div class="col-lg-3 col-md-6">
                    <h3 class="h5 text-uppercase tracking-wider text-secondary mb-4">Progress</h3>
                    <p class="small text-secondary fw-light">Systematic documentation of construction projects from start to finish.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact section -->
    <section class="contact-section py-5 my-5 text-center" id="contact">
        <div class="container px-4 py-5">
            <h2 class="display-2 fw-bold mb-5">Let's Create<br>Something Iconic</h2>
            <div class="d-flex flex-column align-items-center">
                <a href="mailto:hello@visualstories.com" class="display-6 text-decoration-none text-white border-bottom border-2 pb-2 mb-5">hello@visualstories.com</a>
                <div class="d-flex gap-4">
                    <a href="#" class="text-secondary text-decoration-none text-uppercase tracking-widest">Instagram</a>
                    <a href="#" class="text-secondary text-decoration-none text-uppercase tracking-widest">Behance</a>
                    <a href="#" class="text-secondary text-decoration-none text-uppercase tracking-widest">Dribbble</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer py-5 border-top border-secondary border-opacity-10 opacity-50">
        <div class="container px-4 text-center">
            <p class="small m-0 text-secondary">© 2024 VISUAL STORIES. CRAFTED FOR IMPACT.</p>
        </div>
    </footer>
  </div>
</template>

<style scoped>
.tracking-widest {
  letter-spacing: 0.2em;
}

.tracking-wider {
    letter-spacing: 0.1em;
}

.fs-small {
  font-size: 0.8rem;
}

.fs-xsmall {
    font-size: 0.7rem;
}

.bg-card {
    background: var(--bg-card);
}
</style>
