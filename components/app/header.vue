<template>
  <div class="header">
    <div class="header__left">
      <div class="header__hamburger">
        <div class="header__hamburger-line"></div>
        <div class="header__hamburger-line"></div>
        <div class="header__hamburger-line"></div>
      </div>

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
  padding: 0 100px;
  width: 100vw;
  background: white;
  display: flex;
  font-size: 14px;
  position: fixed;
  z-index: 99;
  justify-content: space-between;
  top: 0;
  @media (max-width: 1300px) {
    padding: 0 10px;
  }
  &__hamburger {
    width: 25px;
    height: 15px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    gap: 5px;
    @media (min-width: 1200px) {
      display: none;
    }
    &-line {
      width: 100%;
      height: 3px;
      border-radius: 2px;
      background-color: #30545A;
    }
  }
  &__nav {
    display: flex;
    align-items: center;
    height: 100%;
    color: black;
    @media (max-width: 900px) {
      display: none;
    }
    &-item {
      height: 100%;
      display: flex;
      align-items: center;
      padding: 0 20px;
      transition: 0.2s;
      white-space: nowrap;
      border-bottom: 3px solid white;
      @media (max-width: 1200px) {
        padding: 0 10px;
      }
      &:hover {
        opacity: 0.8;
        cursor: pointer;
        border-bottom: 3px solid #3D4E5C;
      }
    }
  }
  &__left {
    max-width: 300px;
    width: 100%;
    display: flex;
    align-items: center;
    font-weight: 700;
    gap: 20px;
    color: #3D4E5C;
    @media (max-width: 500px) {
      gap: 10px;
    }
    &-text {
      font-size: 14px;
      line-height: 14px;
      font-weight: 500;
      @media (max-width: 500px) {
        font-size: 12px;
        line-height: 12px;
      }
    }
    &-logo {
      cursor: pointer;
      font-size: 24px;
      white-space: nowrap;
      font-weight: 500;
      border-right: 2px solid #3D4E5C;
      padding-right: 10px;
      @media (max-width: 500px) {
        font-size: 20px;
        border-right: none;
        padding-right: 0;
      }
    }
  }
  &__center {
    width: 100%;
    display: flex;
    justify-content: center;
  }
  &__right {
    max-width: 300px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: auto;
  }
}
</style>
