<script setup>
import axios from "axios";
import { ref, onMounted } from 'vue';

const response = ref(null);
const numbers = ref([]);

// Random 3 numbers using a Set
numbers.value = (() => {
  const set = new Set();

  while (true) {
    set.add(Math.floor(Math.random() * 19));

    if (set.size === 3) {
      return set;
    }
  }
})();


onMounted(async () => {
  response.value = await axios.get(`https://api.themoviedb.org/3/movie/now_playing?api_key=${import.meta.env.VITE_TMDB_KEY}`);
})
</script>

<template>
  <div class="movie-gallery">
    <div v-if="response" class="movie-list">
      <div v-for="number in numbers" :key="response.data.results[number].id" class="movie-card">
        <img :src="`https://image.tmdb.org/t/p/w500${response.data.results[number].poster_path}`" alt="Movie Poster" class="movie-poster" />
        <p class="movie-title">{{ response.data.results[number].title }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.movie-gallery {
  display: flex;
  overflow-x: auto;
  padding: 20px;
}

.movie-list {
  display: flex;
  gap: 20px;
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
  font-size: 14px;
  font-weight: bold;
}
</style>