<script setup>
  const query = ref("");
  const movies = ref([]);
  
  async function search() {
    const {Search} = await $fetch(`http://www.omdbapi.com/?apikey=68ccd8ff&s=${query.value}`)
    movies.value = Search;
    
  }
</script>

<template>
  <div>
    <form @submit.prevent>
      <input type="text" v-model="query">
      <button @click="search">Search</button>
    </form>
    <ul class="flex-box">
      <li v-for="movie in movies" :key="movie.imdbID">
        <NuxtLink :to="{name: 'movies-id', params: {id: movie.imdbID}}">
          <img :src="movie.Poster" :alt="movie.title">
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.flex-box {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  list-style: none;
}
</style>