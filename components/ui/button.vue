<template>
  <div>
    <input type="button" class="button" :value="text" :class="buttonTypeClass">
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  type: 'primary' | 'default' | 'primary-outlined',
  text: string
}>()

const buttonTypeClass = computed(() => {
  if (props.type === 'primary') {
    return 'button__primary'
  } else if (props.type === 'default') {
    return 'button__default'
  } else if (props.type === 'primary-outlined') {
    return 'button__primaryOutlined'
  }
})

</script>

<style scoped lang="scss">
.button {
  border-radius: 5px;
  padding: 0 30px;
  font-size: 14px;
  white-space: nowrap;
  transition: 0.3s;
  cursor: pointer;
  height: 40px;
  @media (max-width: 500px) {
    padding: 5px 15px;
  }
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
  &__primaryOutlined {
    color: #30545A;
    border: 2px solid #30545A;
  }
}
</style>
