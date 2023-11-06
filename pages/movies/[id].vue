<script setup>
  const route = useRoute();
  const {data} = useFetch(`http://www.omdbapi.com/?apikey=68ccd8ff&i=${route.params.id}`, {
    pick: ["Plot", "Title"],
    key:`/movies/${route.params.id}`,
})
  

</script>

<template>
  
    <div>
      <pre>
        {{ data }}
      </pre>
    </div>
  
</template>


<style scoped></style>
