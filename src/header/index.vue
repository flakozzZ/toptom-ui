<script lang='ts'>
export default {
  name: 'storybook-header'
}
</script>

<script setup lang='ts'>
import Button from '@/components/Button/Button.vue'
</script>

<template>
  <div class='header'>
    <div class='header__inner'>
      <div class='header__leftSide'>
        <div class='header__info'>
          <div class='header__logo'>Timeline</div>
          <p class='header__text'>Отображает графическую информацию о статусе заказ</p>
        </div>
        <Button size='lg' type='storybook'>Сторибук</Button>
      </div>
      <div class='header__rightSide'>
        <img class='header__image' src='/images/image.png' alt='image'>
      </div>
    </div>
  </div>
</template>

<style scoped lang='scss'>
.header {
  margin-top: 20px;
  width: 1280px;
  height: 387px;
  background: #0F0E14;
  border-radius: 40px;
  color: white;


  &__info {
    display: flex;
    flex-direction: column;
  }

  &__inner {
    display: flex;
    justify-content: space-between;
    padding: 48px 60px;
  }
  &__logo {
    font-size: 48px;
    font-weight: 800;
    margin-bottom: 16px;
  }
  &__text {
    font-size: 24px;
    margin-bottom: 32px;
    letter-spacing: 0.1rem;
  }

}
</style>
