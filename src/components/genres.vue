<template>
    <div class="movie-gallery">
      <label for="genre-select" class="genre-label">Select Genre</label>
      <select id="genre-select" v-model="selectedGenre" @change="getMovieByGenre">
        <option v-for="genre in genres" :key="genre.id" :value="genre.id">{{ genre.name }}</option>
      </select>
  
      <!-- Show loading state -->
      <div v-if="loading" class="loading">Loading...</div>
  
      <!-- Show error message -->
      <div v-if="error" class="error">{{ error }}</div>
  
      <!-- Movie list -->
      <div v-if="response" class="movie-list">
        <div v-for="movie in response.data.results" :key="movie.id" class="movie-card" @click="getMovieDetails(movie.id)">
          <img :src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`" alt="Movie Poster" class="movie-poster" />
          <p class="movie-title">{{ movie.title }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import axios from "axios";
  import { ref, onMounted } from "vue";
  import { useRouter } from "vue-router";
  
  // Define props
  const props = defineProps(["genres"]);
  const router = useRouter();
  
  // Reactive variables
  const selectedGenre = ref(28);
  const response = ref(null);
  const loading = ref(false);
  const error = ref(null);
  
  // Function to fetch movies by selected genre
  async function getMovieByGenre() {
    loading.value = true;
    error.value = null;
    try {
      response.value = await axios.get(
        `https://api.themoviedb.org/3/discover/movie?api_key=${import.meta.env.VITE_TMDB_KEY}&with_genres=${selectedGenre.value}`
      );
    } catch (err) {
      error.value = "Failed to load movies. Please try again later.";
    } finally {
      loading.value = false;
    }
  }
  
  // Function to navigate to the movie details page
  function getMovieDetails(id) {
    router.push(`/movies/${id}`);
  }
  
  // Fetch movies on component mount
  onMounted(() => {
    getMovieByGenre();
  });
  </script>
  
  <style scoped>
  .movie-gallery {
    padding: 20px;
    color: white;
    background-color: #141414;
  }
  
  .movie-gallery h1 {
    text-align: center;
    margin-bottom: 20px;
    font-size: 2.5rem;
  }
  
  .movie-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
  }
  
  .movie-card {
    background-color: #222;
    border-radius: 10px;
    overflow: hidden;
    transition: transform 0.2s;
    width: 200px;
  }
  
  .movie-card:hover {
    transform: scale(1.05);
  }
  
  .movie-poster {
    width: 100%;
    height: auto;
  }
  
  .movie-title {
    padding: 10px;
    text-align: center;
    font-size: 1.1rem;
    color: #e50914;
  }
  
  select {
    background-color: #333;
    color: white;
    padding: 10px;
    border: 2px solid #444;
    border-radius: 5px;
    font-size: 1rem;
    width: 200px;
    margin: 10px 0;
  }
  
  select:focus {
    border-color: #e50914;
    outline: none;
  }
  
  .genre-label {
    color: #e50914;
    font-size: 1.2rem;
    margin-bottom: 10px;
    display: block;
  }
  
  .loading,
  .error {
    color: #e50914;
    text-align: center;
    font-size: 1.2rem;
  }
  </style>
  