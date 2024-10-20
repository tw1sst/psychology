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


          <div class="content__info-bottom">
            <div class="mouse-scroll">
              <div class="mouse">
                <div class="wheel"></div>
              </div>
              <div class="arrow"></div>
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
              Специализируемся на индивидуальной
              психотерапевтической практике в Ростове-на-Дону. Мы сочетаем научно обоснованное методы
              терапии, доброжелательное общение и непринужденную обстановку, чтобы осуществить
              индивидуальный подход.
              Наш квалифицированный тандем предлагает психологически услуги для взрослых. Независимо от
              того, ищете ли вы услуги для себя, любимого человека или сотрудников, мы поможем вам.
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
        <div class="support__title">Готовы начать?</div>

        <div class="steps__grid">
          <div>
            <div class="steps__grid-item">
              <div class="steps__grid-badge">1</div>

              <span class="steps__grid-title">Подберите свою первую консультацию</span>

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

    <div class="contact container">
      <div class="contact__img">
        <img :src="Group3" alt="Contact group">
      </div>

      <div class="contact__form">
        <div>
          <div class="contact__form-title">
            Оставьте заявку на своей первый сеанс прямо сейчас
          </div>

          <div class="contact__form-text">
            Не откладывайте заботу о себе на потом! Заполните заявку на первый сеанс, и начните свой путь к пониманию, гармонии и личностному росту.
          </div>
        </div>

        <div class="contact__form-center">
          <div>
            <label class="contact__form-label">Введите ваше имя</label>
            <UInput class="contact__form-input" placeholder="Ваше имя" style="height: 41px;" />
          </div>

          <div>
            <label class="contact__form-label">Введите ваш номер телефона</label>
            <UInput class="contact__form-input" placeholder="+7 (920) 360-26-54" style="height: 41px;" />
          </div>

          <div>
            <UCheckbox label="Я соглашаюсь на обработку моих персональных данных" />
          </div>
        </div>

        <ui-button type="primary" text="Записаться на бесплатный сеанс" />
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

    <div class="reviews">
      <div class="container">
        <div class="reviews__grid">
          <div class="reviews__left">
            <div class="reviews__left-text">
              Отзывы наших клиентов, реальный опыт работы с психологами
            </div>

            <div class="reviews__left-actions">
              <ui-button @click="carouselReviewsRef.prev()" type="primary" text="Назад" />

              <ui-button @click="carouselReviewsRef.next()" type="primary-outlined" text="Дальше" />
            </div>
          </div>

          <div class="reviews__right">
            <UCarousel ref="carouselReviewsRef" class="reviews__items" v-slot="{ item }" :items="reviews">
              <div class="reviews__items-item">
                <div class="reviews__items-text">
                  {{ item.text }}
                </div>

                <div class="reviews__items-bottom">
                  <img class="reviews__items-avatar" :src="item.avatar" alt="avatar">

                  <div>
                    <div class="reviews__item-author">
                      {{ item.author }}
                    </div>

                    <div class="reviews__items-subtext">
                      {{ item.subtext }}
                    </div>
                  </div>
                </div>
              </div>
            </UCarousel>

            <div class="reviews__left-actionsMobile">
              <ui-button @click="carouselReviewsRef.prev()" type="primary" text="Назад" />

              <ui-button @click="carouselReviewsRef.next()" type="primary-outlined" text="Дальше" />
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
import Group1 from '~/assets/img/group1.jpg'
import Group3 from '~/assets/img/group3.jpg'
import Arrow1 from '~/assets/img/arrow1.jpg'
import Arrow2 from '~/assets/img/arrow2.png'

import Man1 from 'assets/img/avatars/man1.jpg'
import Man2 from 'assets/img/avatars/man2.jpg'
import Man3 from 'assets/img/avatars/man3.jpg'
import Woman1 from 'assets/img/avatars/woman1.jpg'
import Woman2 from '~/assets/img/avatars/woman2.jpg'
import Woman3 from '~/assets/img/avatars/woman3.jpg'
import Woman4 from '~/assets/img/avatars/woman4.jpg'
import Woman5 from '~/assets/img/avatars/woman5.jpg'
import Woman6 from '~/assets/img/avatars/woman6.jpg'

interface ReviewItem {
  id: number;
  text: string;
  author: string;
  subtext: string;
  avatar: string;
}

const carouselRef = ref()
const carouselReviewsRef = ref()

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

const reviews = ref<ReviewItem[]>([
  {
    id: 1,
    text: "Благодаря поддержке психолога я смогла справиться с тревогой и наконец-то начать чувствовать себя уверенно в жизни. Очень благодарна за помощь!",
    author: "Ольга М.",
    subtext: "тревожность",
    avatar: Woman1
  },
  {
    id: 2,
    text: "На консультациях мне помогли взглянуть на свои отношения по-новому. Наши с женой конфликты стали реже, а понимание лучше.",
    author: "Александр П.",
    subtext: "семейные проблемы",
    avatar: Man1
  },
  {
    id: 3,
    text: "Сессии с психологом помогли мне преодолеть эмоциональное выгорание на работе. Теперь чувствую себя гораздо лучше и снова с энтузиазмом иду на работу!",
    author: "Мария К.",
    subtext: "выгорание на работе",
    avatar: Woman2
  },
  {
    id: 4,
    text: "Я пришел с чувством внутренней пустоты и одиночества. После нескольких встреч осознал, что могу и должен работать над собой. Спасибо за верное направление!",
    author: "Андрей С.",
    subtext: "кризис самооценки",
    avatar: Man2
  },
  {
    id: 5,
    text: "После долгого периода депрессии я нашла специалиста, который помог мне выйти из этого состояния. Ощущение, будто снова дышу полной грудью! ",
    author: "Елена В.",
    subtext: "депрессия",
    avatar: Woman3
  },
  {
    id: 6,
    text: "Проработали с психологом мои детские травмы, которые мешали мне строить отношения. Теперь чувствую себя более гармонично и уверенно.",
    author: "Анна Л.",
    subtext: "прошлые травмы",
    avatar: Woman4
  },
  {
    id: 7,
    text: "Я долго не могла разобраться в себе и своих целях, но с помощью специалиста смогла найти внутреннюю гармонию. Это был важный шаг в моей жизни!",
    author: "Виктория Д.",
    subtext: "поиск себя",
    avatar: Woman5
  },
  {
    id: 8,
    text: "После развода было сложно пережить боль и разочарование, но консультации помогли восстановиться и начать новую жизнь.  ",
    author: "Алина К.",
    subtext: "развод и стресс",
    avatar: Woman6
  },
])

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

onMounted(() => {
  setInterval(() => {
    if (!carouselRef.value) return

    if (carouselRef.value.page === carouselRef.value.pages) {
      return carouselRef.value.select(0)
    }

    carouselRef.value.next()
  }, 3000)
})
</script>

<style scoped lang="scss">
.container {
  height: auto;
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
}

.mouse-scroll {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.mouse {
  width: 38px;
  height: 60px;
  border: 3px solid white;
  border-radius: 18px;
  display: flex;
  justify-content: center;
  align-items: start;
  opacity: 0.8;
}

.wheel {
  width: 6px;
  height: 16px;
  background-color: white;
  border-radius: 4px;
  animation: scroll 2s infinite;
  margin-top: 8px;
}

/* Scroll animation */
@keyframes scroll {
  0% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(8px);
  }

  100% {
    transform: translateY(0);
  }
}

.arrow {
  width: 10px;
  height: 10px;
  border-right: 2px solid white;
  border-bottom: 2px solid white;
  transform: rotate(45deg);
}

.reviews {
  padding: 20px;
  @media (max-width: 750px) {
    padding: 0;
  }
  &__grid {
    display: grid;
    grid-template-columns: 450px 1fr;
    padding: 40px 0;
    @media (max-width: 750px) {
      grid-template-columns: 300px 1fr;
    }
    @media (max-width: 750px) {
      grid-template-columns: 1fr;
      gap: 20px;
      padding: 20px 0;
    }
  }
  &__left {
    @media (max-width: 750px) {
      padding: 0 20px;
    }
    &-text {
      font-size: 34px;
    }
    &-actionsMobile {
      display: none;
      @media (max-width: 750px) {
        display: flex;
        gap: 20px;
        width: 100%;
        margin: 20px;
      }
    }
    &-actions {
      display: flex;
      gap: 20px;
      margin-top: 20px;
      @media (max-width: 750px) {
        display: none;
      }
    }
  }
  &__right {
    overflow: hidden;
    display: flex;
    flex-direction: column;
    border-radius: 10px;
  }
  &__items {
    display: flex;
    height: 100%;
    &-avatar {
      height: 48px;
      width: 48px;
      object-fit: cover;
      border-radius: 50%;
    }
    &-text {
      font-size: 18px;
    }
    &-author {
      font-size: 16px;
    }
    &-subtext {
      font-size: 14px;
      color: #3D4E5C;
    }

    &-bottom {
      display: flex;
      align-items: center;
      gap: 10px;
    }
    &-item {
      padding: 10px 20px;
      margin: 0 10px;
      background-color: #F4EEE1;
      border-radius: 10px;
      width: 400px;
      height: 100%;
      display: flex;
      gap: 20px;
      flex-direction: column;
      justify-content: space-between;
      cursor: pointer;
      @media (max-width: 750px) {
        margin-left: 20px;
      }
      @media (max-width: 500px) {
        font-size: 14px;
        width: 320px;
      }
    }
  }
}

.contact {
  display: grid;
  grid-template-columns: 1fr 1fr;
  height: 600px;
  overflow: hidden;
  background-color: #F4EEE2;
  margin-top: 20px;
  margin-bottom: 20px;
  border-radius: 10px;
  &__img {
    height: 600px;
    & img {
      object-fit: cover;
      object-position: center center;
      position: relative;
      height: 100%;
      width: 100%;
    }
  }
  &__form {
    background-color: #F4EEE2;
    padding: 40px;
    width: 100%;
    display: flex;
    gap: 20px;
    flex-direction: column;
    max-height: 600px;
    justify-content: space-between;
    @media (max-width: 500px) {
      padding: 20px;
    }
    &-center {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }
    &-title {
      font-size: 26px;
      margin-bottom: 20px;
    }
    &-text {
      color: #30545A;
    }
    &-input {
      height: 41px;
    }
    &-label {
      color: #30545A;
      font-size: 14px;
    }
  }
}

.questions {
  padding: 40px 20px;
  background-color: #F4EEE2;
  &__list {
    display: flex;
    gap: 20px;
    flex-direction: column;
  }
  &__button {
    color: black;
    height: 41px;
    font-size: 16px;
    background-color: white;
  }
  &__content {
    font-size: 16px;
    color: #30545A;
    padding-top: 20px;
  }
}

.helping {
  padding: 40px 20px;
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
      padding: 20px;
      border-radius: 10px;
      display: flex;
      flex-direction: column;
      gap: 20px;
      position: relative;
      background-color: white;
    }
    &-title {
      font-size: 18px;
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
  &__info {
    width: 100%;
    position: absolute;
    top: 100px;
    height: 100vh;
    flex-direction: column;
    display: flex;
    justify-content: center;
    align-items: center;
    left: 0;
    @media (max-width: 500px) {
      top: 0;
      height: 100vh;
    }
    &-bottom {
      padding: 40px 0;
      @media (max-width: 500px) {
        background-color: rgb(255, 255, 255, 0.7);
        width: 100%;
        padding: 20px 0;
      }
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
        max-height: 100%;
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
      max-width: 500px;
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
