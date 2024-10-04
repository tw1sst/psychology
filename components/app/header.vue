<template>
  <div class="header">
    <div class="header__left">
      <span class="header__left-logo" @click="navigateTo({ name: 'index' })">Я ОКЕЙ</span>
      <span class="header__left-text">центр ментального<br>здоровья</span>
    </div>

    <div class="header__center" v-show="md">
      <ul class="header__nav">
        <li class="header__nav-item" v-for="item in menuItems" :key="item.id">
          {{ item.title }}
        </li>
      </ul>
    </div>

    <div class="header__right">
      <ui-button v-show="lg" type="default" text="+7 (920) 360-26-54" />
      <ui-button type="primary" text="Записаться" />
    </div>
  </div>
</template>


<script setup lang="ts">
import { useMediaQuery } from '@vueuse/core'
import logo from '~/assets/img/logo.png'

interface menuItem {
  id: number,
  title: string,
  path: string,
}

const md = useMediaQuery('(min-width: 767px)')
const lg = useMediaQuery('(min-width: 1024px)')
const xl = useMediaQuery('(min-width: 1280px)')
const menuItems = ref<Array<menuItem>>([
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
  {
    id: 7,
    title: 'Помощь',
    path: 'help'
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
  position: fixed;
  z-index: 99;
  justify-content: space-between;
  top: 0;
  &__nav {
    display: flex;
    align-items: center;
    height: 100%;
    &-item {
      height: 100%;
      display: flex;
      align-items: center;
      padding: 0 20px;
      transition: 0.3s;
      white-space: nowrap;
      &:hover {
        opacity: 0.8;
        cursor: pointer;
        border-bottom: 4px solid #3D4E5C;
      }
    }
  }
  &__left {
    max-width: 275px;
    margin: 0 20px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    gap: 10px;
    color: #3D4E5C;
    &-text {
      font-size: 14px;
      line-height: 14px;
      font-weight: 500;
    }
    &-logo {
      cursor: pointer;
      font-size: 24px;
      white-space: nowrap;
      font-weight: 500;
      border-right: 2px solid #3D4E5C;
      padding-right: 10px;
    }
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
    width: auto;
  }
}
</style>
