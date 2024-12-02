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
  justify-content: center;  /* Centers the gallery horizontally */
  overflow-x: auto;
  padding: 20px;
}

.movie-list {
  display: flex;
  gap: 40px; /* Increased space between movie cards */
  justify-content: center; /* Center the movie cards within the list */
}

.movie-card {
  flex: 0 0 auto;
  width: 200px; /* Adjust the width as needed */
  text-align: center;
}

.movie-poster {
  width: 100%;
  height: auto;
  border-radius: 8px;
}

.movie-title {
  margin-top: 10px;
  font-size: 16px;  /* Adjusted font size */
  font-weight: bold;
}

</style>
