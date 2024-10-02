<template>
  <div class="content">
    <video :src="'https://node-dev.boomstream.com/balancer/zmOWkaee-rC6LADb6/playlist.m3u8'" />
    index page

    <NuxtLink :to="{ name: 'about' }">About</NuxtLink>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped lang="scss">
.content {
  background-color: green;
  height: 100vh;
}
</style>
