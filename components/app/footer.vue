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

        <div class="footer__feedback">
          <div class="footer__feedback-title">Оставьте заявку прямо сейчас!</div>

          <div class="footer__feedback-text">Мы свяжемся с вами максимально бытсро</div>

          <input class="footer__feedback-form" type="tel" placeholder="Введите номер телефона" />

          <ui-button type="primary" text="Записаться сейчас" />
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
</script>

<style scoped lang="scss">
.footer {
  height: auto;
  background: white;
  padding: 40px 100px;
  z-index: 999;
  @media (max-width: 500px) {
    padding: 20px;
  }
  &__container {
    max-width: 1100px;
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
      gap: 40px;
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
    gap: 20px;
    flex-wrap: wrap;
    border-top: 2px solid #30545A;
    border-bottom: 2px solid #30545A;
    padding: 20px 0;
    @media (max-width: 500px) {
      justify-content: center;
    }
    &-item {
      cursor: pointer;
    }
  }
  &__logo {
    background: white;
    width: 150px;
    &-img {
      display: block;
      width: 150px;
      height: 150px;
    }
  }
  &__bottom {
    margin-top: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    @media (max-width: 500px) {
      justify-content: center;
      flex-direction: column;
      gap: 20px;
      text-align: center;
    }
  }
}
</style>
