<script setup>
  const route = useRoute();
  const message = computed(() =>`i'm on team ${route.params.teamSlug} and my user id is ${route.params.userId}`); 
</script>

<template>
  <p>
    {{message}}
  </p>
</template>

<style scoped></style>