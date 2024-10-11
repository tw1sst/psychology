<template>
  <div>
    <div class="content">
      <div class="content__bg">
        <video playsinline autoplay muted loop class="content__bg-video">
          <source :src="BgVideo" type='video/mp4'>
        </video>

        <div class="content__info">
          <div class="content__info-block">
            <img alt="logo" :src="Logo" class="content__info-logo">

            <div class="content__info-text">Интегративная психотерапия <br> в Ростове-на-Дону </div>

            <div class="content__info-subtext">Где наука встречается с душой</div>

            <div>
              <ui-button type="primary" text="Записаться на бесплатный сеанс" />
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="aboutUs">
      <div class="aboutUs__container">
        <div class="aboutUs__content">
          <div class="aboutUs__left">
            <img alt="Person" class="aboutUs__left-person" :src="Person1">
          </div>

          <div class="aboutUs__right">
            <div class="aboutUs__right-title">Подробнее о нас</div>

            <div class="aboutUs__right-separator"></div>

            <div class="aboutUs__right-text">
              Мы занимаемся групповой психотерапевтической практикой в центре Ростова-на-Дону. Мы сочетаем методы лечения, основанные на фактических данных, общение с людьми и непринужденную обстановку, чтобы предложить инклюзивный и индивидуальный подход.
              Наша квалифицированная команда предлагает помощь в сообществе, включая терапевтические услуги для подростков (14+) и взрослых, а также корпоративные оздоровительные программы и поддержку в области психического здоровья на месте. Независимо от того, ищете ли вы услуги и ресурсы для себя, любимого человека или сотрудников, мы поможем вам.
            </div>

            <div class="aboutUs__right-separator"></div>

            <div class="aboutUs__right-actions">
              <ui-button type="primary" text="Записаться прямо сейчас" />

              <ui-button type="primary-outlined" text="Подробнее" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import BgVideo from '~/assets/img/bg-cover3.mp4'
import Logo from '~/assets/img/logo.png'
import Person1 from '~/assets/img/person1.png'
// const footer = useTemplateRef('footer')
</script>

<style scoped lang="scss">
.content {
  &__info {
    width: 100%;
    position: absolute;
    top: 15rem;
    display: flex;
    justify-content: center;
    left: 0;
    &-logo {
      max-height: 200px;
    }
    &-block {
      color: #3D4E5C;
      background-color: rgb(255, 255, 255, 0.7);
      max-width: 500px;
      border-radius: 20px;
      max-height: 500px;
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 20px;
      justify-content: center;
      padding: 40px 20px;
      text-align: center;
      @media (max-width: 500px) {
        border-radius: 0px;
      }
    }
    &-text {
      font-size: 26px;
    }
  }
  &__bg {
    width: 100vw;
    height: 800px;
    padding: 0 20px;
    overflow: hidden;
    @media (max-width: 500px) {
      padding: 0 10px;
    }
    &-video {
      width: 100%;
      height: 100%;
      border-radius: 20px;
      object-fit: cover;
    }
  }
}

.aboutUs {
  display: flex;
  align-items: center;
  padding: 40px 20px;
  @media (max-width: 500px) {
    padding: 20px;
  }
  &__container {
    height: auto;
    max-width: 1100px;
    width: 100%;
    margin: 0 auto;
  }
  &__content {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 40px;
    @media (max-width: 800px) {
      grid-template-columns: 1fr;
      gap: 20px;
    }
    @media (max-width: 500px) {
      display: flex;
      flex-direction: column-reverse;
    }
  }
  &__left {
    display: flex;
    justify-content: center;
    &-person {
      max-width: 450px;
      width: 100%;
      height: 100%;
      border-radius: 20px;
    }
  }
  &__right {
    display: flex;
    gap: 20px;
    justify-content: space-between;
    flex-direction: column;
    &-title {
      font-size: 22px;
    }
    &-separator {
      width: 100%;
      border-bottom: 2px solid #30545A;
    }
    &-text {
      font-size: 18px;
      line-height: 28px;
      @media (max-width: 500px) {
        font-size: 14px;
      }
    }
    &-actions {
      display: flex;
      gap: 20px;
      align-items: center;
      @media (max-width: 500px) {
        gap: 10px;
      }
    }
  }
}
</style>
