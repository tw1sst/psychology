<template>
  <div class="footer">
    <div class="footer__container">
      <div class="footer__head">
        <div class="footer__logo">
          <img :src="logo" alt="logo" class="footer__logo-img" />
        </div>

        <div class="footer__actions">
          <ul class="footer__nav">
            <li class="footer__nav-item" v-for="item in menuItems" :key="item.id">
              {{ item.title }}
            </li>
          </ul>
        </div>

        <div class="footer__up">
          <button @click="goTop" class="footer__up-button">
            ⬆
          </button>
        </div>
      </div>

      <div class="footer__social">
        <div class="footer__social-medias">
          <img :src="whatsappLogo" alt="whatsappLogo" class="footer__social-media">

          <img :src="telegramLogo" alt="telegramLogo" class="footer__social-media">
        </div>

        <div class="footer__social-phone">
          +7 (920) 360-26-54
        </div>
      </div>

      <div class="footer__bottom">
        <div>Центр ментального здоровья в Ростове-на-Дону</div>
        <div>Я ОКЕЙ - Copyright © 2024</div>
      </div>

    </div>
  </div>
</template>

<script setup lang="ts">
import logo from '~/assets/img/logo.png'
import telegramLogo from '~/assets/img/telegram.png'
import whatsappLogo from '~/assets/img/whatsapp.png'

interface menuItem {
  id: number,
  title: string,
  path: string,
}

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

const goTop = () => {
  window.scrollTo({
    top: 0,
    left: 0,
    behavior: 'smooth'
  });
}
</script>

<style scoped lang="scss">
.footer {
  height: auto;
  background: #F4EEE1;
  padding: 40px 100px;
  z-index: 999;
  color: black;
  @media (max-width: 500px) {
    padding: 20px;
  }
  &__social {
    margin-top: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    @media (max-width: 500px) {
      flex-direction: column;
    }
    &-phone {
      font-size: 36px;
    }
    &-medias {
      display: flex;
      gap: 10px;
    }
    &-media {
      width: 34px;
      height: 34px;
      opacity: 0.5;
      transition: 0.3s;
      &:hover {
        opacity: 1;
        cursor: pointer;
      }
    }
  }
  &__up {
    &-button {
      width: 38px;
      height: 38px;
      border: 2px solid rgba(48, 84, 90, 1);
      border-radius: 5px;
      color: rgba(48, 84, 90, 1);
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      transition: 0.3s;
      &:hover {
        opacity: 0.8;
      }
    }
  }
  &__container {
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
  }
  &__head {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 20px;
    @media (max-width: 500px) {
      justify-content: center;
    }
  }
  &__feedback {
    display: flex;
    flex-direction: column;
    gap: 15px;
    @media (max-width: 500px) {
      align-items: center;
    }
    &-title {
      font-size: 22px;
      color: black;
    }
    &-text {
      color: #30545A;
    }
    &-form {
      padding: 15px;
      height: 37px;
      border-radius: 5px;
      color: #30545A;
      border: 2px solid #30545A;
      &::placeholder {
        color: #30545A;
      }
      @media (max-width: 500px) {
        width: 100%;
      }
    }
  }
  &__nav {
    display: flex;
    gap: 40px;
    flex-wrap: wrap;
    padding: 20px 0;
    @media (max-width: 500px) {
      justify-content: center;
      gap: 20px;
    }
    &-item {
      cursor: pointer;
      transition: 0.3s;
      &:hover {
        color: #3D4E5C;
      }
    }
  }
  &__logo {
    background: white;
    padding: 10px;
    border-radius: 10px;
    display: none;
    @media (max-width: 750px) {
      display: none;
    }
    &-img {
      display: block;
      width: 100px;
      height: 100px;
    }
  }
  &__bottom {
    margin-top: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #3D4E5C;
    @media (max-width: 500px) {
      justify-content: center;
      flex-direction: column;
      gap: 20px;
      text-align: center;
    }
  }
}
</style>
