<script setup>
import axios from "axios";
import { useRoute } from "vue-router";

const route = useRoute();
const response = await axios.get(`https://api.themoviedb.org/3/movie/${route.params.id}?api_key=${import.meta.env.VITE_TMDB_KEY}&append_to_response=videos`);
console.log(response.data);
</script>

<template>
  <div class="movie-detail">
    <h1 class="movie-title">{{ response.data.original_title }}</h1>
    <p class="movie-overview">{{ response.data.overview }}</p>
    <p class="movie-release-date">Release Date: {{ response.data.release_date }}</p>
    <a class="movie-site" :href="response.data.homepage" target="_blank">Official Movie Site</a>
    <img :src="`https://image.tmdb.org/t/p/w500${response.data.poster_path}`" alt="Movie Poster" class="movie-poster" />

    <h2 class="trailers-title">Trailers</h2>
    <div class="trailers-container">
      <div v-for="trailer in response.data.videos.results" :key="trailer.id" class="trailer-tile">
        <a :href="`https://www.youtube.com/watch?v=${trailer.key}`" target="_blank">
          <img :src="`https://img.youtube.com/vi/${trailer.key}/hqdefault.jpg`" alt="Trailer"
            class="trailer-thumbnail" />
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.movie-detail {
  padding: 20px;
  color: white;
  background-color: #141414; /* Netflix dark gray for the detail view background */
}

.movie-title {
  font-size: 2.5rem;
  margin-bottom: 10px;
  color: #e50914; 
  font-weight: bold; 
}

.movie-overview {
  font-size: 1.2rem;
  margin-bottom: 10px;
  color: #d3d3d3; 
}

.movie-release-date {
  font-size: 1rem;
  margin-bottom: 20px;
  color: #d3d3d3;
}

.movie-site {
  display: inline-block;
  margin-bottom: 20px;
  padding: 10px 15px;
  background-color: #e50914; 
  color: white; 
  text-decoration: none;
  border-radius: 5px;
  font-weight: bold;
  transition: background-color 0.3s, transform 0.2s;
}

.movie-site:hover {
  background-color: #f40612;
  transform: scale(1.05); 
}

.movie-poster {
  width: 25%;
  border-radius: 10px;
  margin-bottom: 20px;
  border: 3px solid #333; 
}

.trailers-title {
  font-size: 2rem;
  margin-top: 40px;
  margin-bottom: 20px;
  text-align: center;
  color: white;
  font-weight: bold;
}

.trailers-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 15px;
}

.trailer-tile {
  background-color: #222; 
  border-radius: 10px;
  overflow: hidden;
  transition: transform 0.2s, box-shadow 0.3s;
  width: 200px; 
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3); 
}

.trailer-tile:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.4); 
}

.trailer-thumbnail {
  width: 100%; 
  height: auto; 
  border-bottom: 2px solid #e50914; 
}
</style>
