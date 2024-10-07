<template>
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
</template>

<script setup lang="ts">
import BgVideo from '~/assets/img/bg-cover3.mp4'
import Logo from '~/assets/img/logo.png'
</script>

<style scoped lang="scss">
.content {
  &__info {
    width: 100%;
    position: absolute;
    top: 15rem;
    display: flex;
    justify-content: center;
    &-logo {
      max-height: 200px;
    }
    &-block {
      color: #3D4E5C;
      background-color: rgb(255, 255, 255, 0.7);
      max-width: 500px;
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
    }
    &-subtext {

    }
    &-text {
      font-size: 26px;
    }
  }
  &__bg {
    width: 100vw;
    height: 800px;
    &-video {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}

.aboutUs {
  height: 500px;
}
</style>
