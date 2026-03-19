<script setup>
const scenes = [
  { number: '1', image: './src/im2.PNG' },
  { number: '2', image: './src/im3.PNG' },
  { number: '3', image: './src/im4.PNG' },
  { number: '4', image: './src/im5.PNG' },
  { number: '5', image: './src/im6.PNG' },
  { number: '6', image: './src/im7.PNG' },
  { number: '7', image: './src/im8.PNG' },
  { number: '8', image: './src/im9.PNG' },
  { number: '9', image: './src/im10.PNG'},
  { number: '10', image: './src/im11.PNG'},
  { number: '11', image: './src/im1.PNG' } 
];
</script>

<template>
  <div class="page-wrapper">
    <header class="hero-section">
      <div class="hero-overlay"></div>
      <div class="container hero-content">
        <h1 class="hero-title">Journey in <br class="mobile-only"> Al-Shawakah</h1>
        <p class="hero-subtitle">Made by Bahaa Abbas</p>
       
      </div>
    </header>

    <main class="container main-content">
      <div class="scenes-list">
        <section v-for="scene in scenes" :key="scene.number" class="scene-item">
          <div class="scene-number">{{ scene.number }}</div>

          <div class="image-container">
            <img 
              :src="scene.image" 
              :alt="`Scene ${scene.number}`" 
              class="scene-image" 
            />
          </div>
        </section>
      </div>
    </main>
  </div>
</template>

<style scoped>

.page-wrapper {
  min-height: 100vh;
  background-color: #13273f;
  color: white;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  
  padding-bottom: env(safe-area-inset-bottom);
}
.hero-subtitle {
  margin-top: 1rem;
  font-size: 0.875rem; 
  color: #9c938a; 
  letter-spacing: 0.1em;
  text-transform: uppercase; 
}


@media (min-width: 768px) {
  .hero-subtitle {
    font-size: 1rem; 
    margin-top: 1.5rem;
  }
}
.container {
  max-width: 1152px;
  margin: 0 auto;
  padding: 0 1.25rem; 
}


.hero-section {
  position: relative;
  overflow: hidden;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  
  padding-top: env(safe-area-inset-top);
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to bottom, rgba(255, 255, 255, 0.05), transparent);
}

.hero-content {
  position: relative;
  padding-top: 3.5rem;
  padding-bottom: 3.5rem;
  text-align: center;
}

.hero-title {
  font-size: 2.1rem; 
  font-weight: 700;
  line-height: 1.1;
  letter-spacing: -0.02em;
}

.mobile-only {
  display: block;
}


.main-content {
  padding-top: 3rem;
  padding-bottom: 3rem;
}

.scenes-list {
  display: flex;
  flex-direction: column;
  gap: 4rem; 
}

.scene-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.scene-number {
  margin-bottom: 1rem;
  font-size: 0.9rem;
  letter-spacing: 0.4em;
  color: rgba(255, 255, 255, 0.5);
  font-weight: 300;
}


.image-container {
  width: 100%;
  max-width: 1024px;
  overflow: hidden;
  border-radius: 1.25rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  background-color: rgba(255, 255, 255, 0.03);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
}

.scene-image {
  width: 100%;
  height: auto;
  display: block;
  object-fit: contain;
}


@media (min-width: 768px) {
  .container {
    padding: 0 1.5rem;
  }
  .hero-content {
    padding-top: 7rem;
    padding-bottom: 7rem;
  }
  .hero-title {
    font-size: 3.75rem;
  }
  .mobile-only {
    display: none;
  }
  .scenes-list {
    gap: 8rem;
  }
  .image-container {
    border-radius: 1.5rem;
  }
  .scene-number {
    font-size: 1.125rem;
    margin-bottom: 1.5rem;
  }
}
</style>