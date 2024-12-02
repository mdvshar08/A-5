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
    id: 12,
    genreName: "Adventure"
  },
  {
    id: 27,
    genreName: "Horror"
  },
  {
    id: 10751,
    genreName: "Family"
  },
  {
    id: 36,
    genreName: "History"
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