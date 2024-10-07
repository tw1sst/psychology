<template>
  <div>
    <app-header />

    <div class="slot">
      <slot/>
    </div>

    <app-footer />
  </div>
</template>

<style scoped lang="scss">

.slot {
  margin-top: 50px;
  display: block;
}

</style>


<script setup lang="ts">
</script>
