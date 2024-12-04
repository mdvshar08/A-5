<script setup>
import Feature from '../components/features.vue'
import Footer from '../components/footer.vue'
import Header from '../components/header.vue'
import Hero from '../components/hero.vue'
</script>

<template>
    <div>
        <Header />
        <Hero />
        <Feature />
        <Footer />
    </div>
</template>

<style scoped>
.movie-gallery {
  display: flex;
  justify-content: center;  
  overflow-x: auto;
  padding: 20px;
}

.movie-list {
  display: flex;
  gap: 40px; 
  justify-content: center; 
}

.movie-card {
  flex: 0 0 auto;
  width: 200px; 
  text-align: center;
}

.movie-poster {
  width: 100%;
  height: auto;
  border-radius: 8px;
}

.movie-title {
  margin-top: 10px;
  font-size: 16px; 
  font-weight: bold;
}

</style>
