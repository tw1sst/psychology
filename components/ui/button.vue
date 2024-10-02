<template>
  <button class="button" :class="buttonTypeClass">
    <slot />
  </button>
</template>

<script lang="ts" setup>
const props = defineProps<{
  type: 'primary' | 'danger',
}>()

const buttonTypeClass = computed(() => {
  return props.type === 'primary' ? 'button__primary' : 'button__danger'
})

</script>

<style scoped lang="scss">
.button {
  border-radius: 5px;
  padding: 10px 20px;
  font-size: 14px;
  &__primary {
    color: white;
    background-color: #30545A;
  }
}
</style>
