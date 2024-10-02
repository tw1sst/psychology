<template>
  <div class="header">
    <div class="header__left">
      <span>Я ОКЕЙ</span>
    </div>

    <div class="header__center">
      <ul class="header__nav">
        <li class="header__nav-item" v-for="item in menuItems" :key="item.id">
          {{ item.title }}
        </li>
      </ul>
    </div>

    <div class="header__right">
      <ui-button type="primary" @click="console.log('click 1')">Записаться</ui-button>
    </div>
  </div>
</template>


<script setup lang="ts">
import logo from '~/assets/img/logo.png'

const menuItems = ref([
  {
    id: 1,
    title: 'Главная',
    path: 'home'
  },
  {
    id: 2,
    title: 'О нас',
    path: 'about'
  },
  {
    id: 3,
    title: 'Сервисы',
    path: 'services'
  },
  {
    id: 4,
    title: 'FAQ',
    path: 'faq'
  },
  {
    id: 5,
    title: 'Контакты',
    path: 'contacts'
  },
  {
    id: 6,
    title: 'Блог',
    path: 'blog'
  },
])
</script>

<style scoped lang="scss">
.header {
  height: 50px;
  width: 100vw;
  background: white;
  display: flex;
  font-size: 14px;
  &__nav {
    display: flex;
    align-items: center;
    height: 100%;
    gap: 40px;
    &-item {
      &:hover {
        cursor: pointer;
      }
    }
  }
  &__left {
    max-width: 200px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
  }
  &__center {
    width: 100%;
    display: flex;
    justify-content: center;
  }
  &__right {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 20px;
    max-width: 200px;
    width: 100%;
  }
}
</style>
