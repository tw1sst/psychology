<template>
  <div class="content">
    <div class="content__bg">
      <video playsinline autoplay muted loop class="content__bg-video">
        <source :src="BgVideo" type='video/mp4'>
      </video>
    </div>
    index page

    <NuxtLink :to="{ name: 'about' }">About</NuxtLink>
  </div>
</template>

<script setup lang="ts">
import BgVideo from '~/assets/img/bg-cover.mp4'
</script>

<style scoped lang="scss">
.content {
  background-color: green;
  height: 100vh;
  &__bg {
    width: 100vw;
    height: 800px;
    &-video {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}
</style>
