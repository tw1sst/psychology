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
        <div class="aboutUs__title">Подробнее о нас</div>

        <div class="aboutUs__content">
          <div class="aboutUs__left">
            <img alt="Person" class="aboutUs__left-person" :src="Group1">
          </div>

          <div class="aboutUs__right">
            <div class="aboutUs__right-text">
              Мы – центр ментального здоровья "Я Окей".<br><br>

              Специализируемся на индивидуальной
              психотерапевтической практике в Ростове-на-Дону. Мы сочетаем научно обоснованное методы
              терапии, доброжелательное общение и непринужденную обстановку, чтобы осуществить
              индивидуальный подход.
              Наш квалифицированный тандем предлагает психологически услуги для взрослых. Независимо от
              того, ищете ли вы услуги для себя, любимого человека или сотрудников, мы поможем вам.
            </div>

<!--            <div class="aboutUs__right-actions">-->
<!--              <ui-button type="primary" text="Записаться прямо сейчас" />-->

<!--              <ui-button type="primary-outlined" text="Подробнее" />-->
<!--            </div>-->
          </div>
        </div>
      </div>
    </div>

    <div class="supportAs">
      <div class="supportAs__title">Осуществляем поддержку в следующих вопросах</div>

      <UCarousel ref="carouselRef" v-slot="{ item }" :items="supportAsItems" class="supportAs__items">
        <div class="supportAs__items-item">{{ item.title }}</div>
      </UCarousel>
    </div>

  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import BgVideo from '~/assets/img/bg-cover3.mp4'
import Logo from '~/assets/img/logo.png'
import Group1 from '~/assets/img/group1.jpg'
const pageYOffset = ref<number>(0)
const carouselRef = ref()

const supportAsItems = [
  { id: 1, title: 'тревожные состояния' },
  { id: 2, title: 'депрессия, подавленность, безвыходность, одиночество' },
  { id: 3, title: 'избавление от созависимости' },
  { id: 4, title: 'семейные проблемы, конфликты, разводы' },
  { id: 5, title: 'проблемы с сексуальными, интимными отношениями' },
  { id: 6, title: 'вина' },
  { id: 7, title: 'ревность' },
  { id: 8, title: 'неуверенность в себе (Негативная самооценка)' },
  { id: 9, title: 'поиск себя, обретение смысла жизни' },
  { id: 10, title: 'самореализация в профессиональной сфере, поиск подходящей работы' },
  { id: 11, title: 'трудности принятия решений, сомнения' },
  { id: 12, title: 'проблемы с достижением целей' },
  { id: 13, title: 'вопросы связанные с воспитанием детей' },
  { id: 14, title: 'поддержка беременных и молодых мам' },
  { id: 15, title: 'перемены в жизни' },
  { id: 16, title: 'травма' },
]

const handleScroll = (event: any) => {
  // && (pageYOffset.value % 30 === 0 || pageYOffset.value % 30 === 0.5)
  if (pageYOffset.value > window.pageYOffset) {
    carouselRef.value.next()
  } else {
    carouselRef.value.prev()
  }
  pageYOffset.value = window.pageYOffset
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted (() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped lang="scss">
.container {
  height: auto;
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
}

.supportAs {
  padding: 40px 0;
  &__title {
    font-size: 26px;
    padding-bottom: 40px;
    text-align: center;
    @media (max-width: 500px) {
      font-size: 22px;
      padding-bottom: 20px;
    }
  }
  &__items {
    display: flex;
    gap: 20px;
    &-item {
      padding: 5px 20px;
      margin: 0 10px;
      background-color: #EAEAEB;
      border-radius: 10px;
      width: 300px;
      text-align: center;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      @media (max-width: 500px) {
        font-size: 14px;
        width: 180px;
        padding: 5px 10px;
      }
    }
  }
}

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
        border-radius: 0;
      }
    }
    &-text {
      font-size: 26px;
    }
  }
  &__bg {
    width: 100vw;
    height: 100vh;
    margin-top: -50px;
    overflow: hidden;
    &-video {
      width: 100%;
      height: 100%;
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
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
  }
  &__content {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 40px;
    align-items: center;
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
      max-width: 500px;
      width: 100%;
      height: 100%;
      border-radius: 10px;
    }
  }
  &__title {
    font-size: 26px;
    padding-bottom: 40px;
    text-align: center;
    @media (max-width: 500px) {
      font-size: 22px;
      padding-bottom: 20px;
    }
  }
  &__right {
    display: flex;
    gap: 20px;
    justify-content: space-between;
    flex-direction: column;
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

.partners {
  margin: 20px 0;
  &__title {
    font-size: 26px;
    text-align: center;
    margin-bottom: 40px;
    @media (max-width: 500px) {
      font-size: 22px;
    }
  }
}
</style>
