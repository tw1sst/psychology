<template>
  <div>
    <loading-page v-if="loading" />

    <div v-else>
      <app-header />

      <div class="slot">
        <slot/>
      </div>

      <app-footer />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const loading = ref<boolean>(true)

onMounted(async () => {
  await nextTick(() => {
    loading.value = false
  })
})
</script>

<style scoped lang="scss">
.slot {
  margin-top: 50px;
  display: block;
}
</style>
