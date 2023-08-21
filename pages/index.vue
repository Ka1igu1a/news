<template>
  <NewsList :pageTitle="'Новости'"></NewsList>
</template>

<script>
import NewsList from '@/components/NewsList.vue'

export default {
  name: 'IndexPage',
  components: {
    NewsList
  }
}
</script>

<style scoped>

</style>

// Global
<style>
* {
  font-size: 10px;
}
</style>
