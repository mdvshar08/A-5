<script setup>
import Footer from '../components/footer.vue'
import Header from '../components/header.vue'
import Genres from '../components/genres.vue'

const genresList = [
  {
    id: 28,
    genreName: "Action"
  },
  {
    id: 878,
    genreName: "Sci-Fi"
  },
  {
    id: 27,
    genreName: "Horror"
  },
  {
    id: 35,
    genreName: "Comedy"
  },
  {
    id: 10749,
    genreName: "Romance"
  },
]
</script>

<template>
<div>
    <Header />
    <Genres :genres="genresList" />
    <Footer />
  </div>
  </template>

<style scoped>

</style>