<template>
  <div>
    <input type="button" class="button" :value="text" :class="buttonTypeClass">
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  type: 'primary' | 'default',
  text: string
}>()

const buttonTypeClass = computed(() => {
  return props.type === 'primary' ? 'button__primary' : 'button__default'
})

</script>

<style scoped lang="scss">
.button {
  border-radius: 5px;
  padding: 10px 30px;
  font-size: 14px;
  white-space: nowrap;
  transition: 0.3s;
  cursor: pointer;
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
