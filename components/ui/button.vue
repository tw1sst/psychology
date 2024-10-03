<template>
  <button class="button" :class="buttonTypeClass">
    <slot />
  </button>
</template>

<script lang="ts" setup>
const props = defineProps<{
  type: 'primary' | 'default',
}>()

const buttonTypeClass = computed(() => {
  return props.type === 'primary' ? 'button__primary' : 'button__default'
})

</script>

<style scoped lang="scss">
.button {
  border-radius: 5px;
  padding: 10px 20px;
  font-size: 14px;
  white-space: nowrap;
  transition: 0.3s;
  &:hover {
    opacity: 0.8;
  }
  &__primary {
    color: white;
    background-color: #30545A;
  }
  &__default {
    color: black;
    background-color: none;
  }
}
</style>
