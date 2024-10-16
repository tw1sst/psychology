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

    <div class="about">
      <div class="about__container">
        <div class="about__title">
          <span>Немного о нас</span>

          <img class="about__arrow" :src="Arrow2" alt="arrow2">
        </div>

        <div class="about__content">
          <div class="about__left">
            <img alt="Person" class="about__left-person" :src="Group1">
          </div>

          <div class="about__right">
            <div class="about__right-text">
              Мы – центр ментального здоровья "Я Окей".<br><br>
              <UDivider /><br>
              Специализируемся на индивидуальной
              психотерапевтической практике в Ростове-на-Дону. Мы сочетаем научно обоснованное методы
              терапии, доброжелательное общение и непринужденную обстановку, чтобы осуществить
              индивидуальный подход.
              Наш квалифицированный тандем предлагает психологически услуги для взрослых. Независимо от
              того, ищете ли вы услуги для себя, любимого человека или сотрудников, мы поможем вам.
              <br><br><UDivider />
            </div>

          </div>
        </div>
      </div>
    </div>

    <div class="support">
      <div class="support__title">Кому будет полезно?</div>

      <UCarousel ref="carouselRef" v-slot="{ item }" :items="useFullItems" class="support__items">
        <div class="support__items-item">{{ item.title }}</div>
      </UCarousel>
    </div>

    <div class="steps">
      <div class="container">
        <div class="steps__grid">
          <div>
            <div class="steps__grid-item">
              <div class="steps__grid-badge">1</div>

              <span class="steps__grid-title">Посетите свою первую консультацию</span>

              <span class="steps__grid-text">Выберите психолога с котором хотели бы работать.</span>
            </div>
          </div>

          <div>
            <div class="steps__grid-item">
              <div class="steps__grid-badge">2</div>

              <span class="steps__grid-title">Запишитесь на бесплатную консультацию</span>

              <span class="steps__grid-text">Во время бесплатной 15-минутной консультации у вас будет возможность обсудить интересующие
вас вопросы, узнать, какие услуги вам нужны, а также почувствовать контакт с клиентом.</span>
            </div>
          </div>

          <div>
            <div class="steps__grid-item">
              <div class="steps__grid-badge">3</div>

              <span class="steps__grid-title">Посетите свою первую психологическую консультацию.</span>

              <span class="steps__grid-text">Мы договоримся о целях работы, процессе планирования встреч, о том как связываться с
терапевтом и производить оплату.</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="helping">
      <div class="container">
        <div class="helping__grid">
          <div class="helping__grid-left">
            <div>Осуществляем поддержку в следующих вопросах:</div>

            <div class="helping__grid-bottom">
              <img alt="arrow" :src="Arrow1" class="helping__grid-arrow">
            </div>
          </div>

          <ul class="helping__grid-list">
            <li>тревожные состояния;</li>
            <li>депрессия, подавленность, безвыходность, одиночество;</li>
            <li>избавление от созависимости;</li>
            <li>семейные проблемы, конфликты, разводы;</li>
            <li>проблемы с сексуальными, интимными отношениями;</li>
            <li>вина;</li>
            <li>ревность;</li>
            <li>неуверенность в себе (Негативная самооценка);</li>
            <li>поиск себя, обретение смысла жизни;</li>
          </ul>

          <ul class="helping__grid-list">
            <li>самореализация в профессиональной сфере, поиск подходящей работы;</li>
            <li>трудности принятия решений, сомнения;</li>
            <li>проблемы с достижением целей;</li>
            <li>вопросы связанные с воспитанием детей;</li>
            <li>поддержка беременных и молодых мам;</li>
            <li>перемены в жизни;</li>
            <li>травма;</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="questions">
      <div class="container">
        <div class="about__title">
          <span>Часто задаваемые вопросы</span>
        </div>

        <UAccordion
          class="questions__list"
          :items="questions"
        >
          <template #default="{ item, index, open }">
            <UButton class="questions__button">
              <span class="truncate">{{ index + 1 }}. {{ item.label }}</span>

              <template #trailing>
                <UIcon
                    name="i-heroicons-chevron-right-20-solid"
                    class="w-5 h-5 ms-auto transform transition-transform duration-200"
                    :class="[open && 'rotate-90']"
                />
              </template>
            </UButton>
          </template>

          <template #item="{ item }">
            <p class="questions__content">
              {{ item.content }}
            </p>
          </template>
        </UAccordion>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import BgVideo from '~/assets/img/bg-cover3.mp4'
import Logo from '~/assets/img/logo.png'
import Group1 from '~/assets/img/group1.jpg'
import Arrow1 from '~/assets/img/arrow1.jpg'
import Arrow2 from '~/assets/img/arrow2.png'
const carouselRef = ref()

const supportAsItems = [
  { id: 1, title: 'тревожные состояния' },
  { id: 2, title: 'депрессия, подавленность, безвыходность, одиночество' },
  { id: 3, title: 'избавление от созависимости' },
  { id: 4, title: 'семейные проблемы, конфликты, разводы' },
  { id: 5, title: 'проблемы с сексуальными, интимными отношениями' },
  { id: 6, title: 'Вина, травма, ревность' },
  { id: 7, title: 'неуверенность в себе (Негативная самооценка)' },
  { id: 8, title: 'поиск себя, обретение смысла жизни' },
  { id: 9, title: 'самореализация в профессиональной сфере, поиск подходящей работы' },
  { id: 10, title: 'трудности принятия решений, сомнения' },
  { id: 11, title: 'проблемы с достижением целей' },
  { id: 12, title: 'вопросы связанные с воспитанием детей' },
  { id: 13, title: 'поддержка беременных и молодых мам' },
  { id: 14, title: 'перемены в жизни' },
]

const useFullItems = [
  { id: 1, title: 'Тем, кто хочет научиться лучше управлять эмоциями' },
  { id: 2, title: 'Людям на пути к личностному росту' },
  { id: 3, title: 'Тем, кто хочет улучшить качество своей жизни' },
  { id: 4, title: 'Людям, стремящимися с изменениями' },
  { id: 5, title: 'Семьям и парам, стремящимися к улучшению отношений' },
  { id: 6, title: 'Людям, испытывающим творческие блоки' },
  { id: 7, title: 'Слушателям своих внутренних переживаний' },
  { id: 8, title: 'Тем, кто ищет поддержку в принятии решений' },
]

onMounted(() => {
  setInterval(() => {
    if (!carouselRef.value) return

    if (carouselRef.value.page === carouselRef.value.pages) {
      return carouselRef.value.select(0)
    }

    carouselRef.value.next()
  }, 3000)
})

const questions = [
  {
    label: 'Проводите ли вы консультации очно и онлайн?',
    content: 'Да! У нас есть кабинет. Мы предлагаем онлайн встречи для клиентов со всего мира.'
  },
  {
    label: 'Сколько длятся сеансы психотерапии?',
    content: 'Наша стандартная продолжительность сеанса - 60 минут. При необходимости мы также предлагаем 30-минутные, и 90-минутные сеансы.'
  },
  {
    label: 'Как часто я встречаюсь со своим психотерапевтом?',
    content: 'Мы выяснили, что большинство клиентов добиваются наибольшего успеха при еженедельной психотерапии. После курса терапии клиенты могут переходит в режим поддерживающих встреч раз в две недели, раз в месяц.'
  },
  {
    label: 'Как мне узнать, какой терапевт в "Я ОКЕЙ" подходит мне больше всего?',
    content: 'Изучите информацию о каждом из наших терапевтов, чтобы узнать, какой из них подходит именно вам. Если вы не уверены на 100%, запишитесь на бесплатную 15 минутную консультацию.'
  },
  {
    label: 'Каковы ваши правила отмены приема?',
    content: 'Если вам необходимо отменить или перенести прием, пожалуйста, сообщите об этом своему терапевту как можно скорее. Необходимо уведомить терапевта за 24 часа, чтобы избежат взимания платы за отмену сеанса в размере полной стоимости запланированной встречи.'
  },
  {
    label: 'Какие формы оплаты вы принимаете?',
    content: 'Мы принимаем наличный, безналичный расчет, а также перевод.'
  }
]
</script>

<style scoped lang="scss">
.container {
  height: auto;
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
}

.questions {
  padding: 40px 20px;
  background-color: white;
  &__list {
    display: flex;
    gap: 20px;
    flex-direction: column;
  }
  &__button {
    height: 41px;
    background-color: #F4EEE2;
    color: black;
  }
  &__content {
    font-size: 16px;
    color: #30545A;
    padding-top: 20px;
  }
}

.helping {
  padding: 40px 20px;
  background-color: white;
  &__grid {
    display: grid;
    gap: 20px;
    grid-template-columns: repeat(3, minmax(300px, 1fr));
    @media (max-width: 1000px) {
      grid-template-columns: repeat(2, minmax(300px, 1fr));
    }
    @media (max-width: 650px) {
      grid-template-columns: repeat(1, minmax(300px, 1fr));
      gap: 10px;
    }
    &-left {
      font-size: 34px;
      display: flex;
      flex-direction: column;
      gap: 20px;
      justify-content: center;
    }
    &-list {
      display: flex;
      flex-direction: column;
      gap: 10px;
      list-style: outside;
      @media (max-width: 650px) {
        margin: 0 20px;
      }
    }
    &-arrow {
      height: 150px;
      @media (max-width: 650px) {
        display: none;
      }
    }
    &-bottom {
      display: flex;
      justify-content: center;
    }
  }
}

.steps {
  padding: 40px 20px;
  background-color: #F4EEE1;
  &__grid {
    display: grid;
    gap: 40px;
    grid-template-columns: repeat(3, minmax(300px, 1fr));
    @media (max-width: 1020px) {
      gap: 20px;
      grid-template-columns: repeat(1, minmax(300px, 1fr));
    }
    &-item {
      background-color: white;
      padding: 20px;
      border-radius: 10px;
      display: flex;
      flex-direction: column;
      gap: 20px;
      position: relative;
    }
    &-title {
      font-size: 18px;
      color: black;
    }
    &-text {
      color: #3D4E5C;
    }
    &-badge {
      width: 30px;
      height: 30px;
      position: absolute;
      background-color: #30545A;
      border-radius: 50%;
      left: -10px;
      top: -10px;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
    }
  }
}

.support {
  padding: 40px 0;
  color: black;
  background-color: white;
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
      padding: 10px 20px;
      margin: 0 10px;
      background-color: #F4EEE1;
      border-radius: 10px;
      width: 300px;
      text-align: center;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      @media (max-width: 500px) {
        font-size: 14px;
        width: 220px;
        padding: 5px 10px;
      }
    }
  }
}

.content {
  color: black;
  &__info {
    width: 100%;
    position: absolute;
    top: 15rem;
    display: flex;
    justify-content: center;
    left: 0;
    @media (max-width: 500px) {
      top: 200px;
    }
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

.about {
  color: black;
  display: flex;
  align-items: center;
  padding: 20px 20px 40px 20px;
  background-color: white;
  @media (max-width: 500px) {
    padding: 20px;
  }
  &__container {
    height: auto;
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
  }
  &__arrow {
    height: 100px;
    @media (max-width: 500px) {
      height: 50px;
    }
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
      max-width: 550px;
      width: 100%;
      height: 100%;
      border-radius: 10px;
    }
  }
  &__title {
    font-size: 26px;
    padding-bottom: 20px;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
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

</style>
