<script lang='ts'>
export default {
  name: 'progress-bar'
}
</script>


<script setup lang='ts'>
import CircleComponent from '@/components/circle/index.vue'
import { ref } from 'vue'

const item = ref([
  {key: 'Created', text: 'Создан', isActive: true,},
  {key: 'Paid', text: 'Оплачен', isActive: true,},
  {key: 'Getting ready', text: 'Готовиться к отправке', isActive: false,},
  {key: 'Get ready', text: 'Готов к отправке', isActive: false,},
  {key: 'In road', text: 'Готов к отправке', isActive: false,},
  {key: 'In road', text: 'В пути', isActive: false,},
  {key: 'Done', text: 'Доставлен', isActive: false,},
])
</script>

<template>
  <div class='main'>
    <div class='main__inner'>
      <circle-component :items='item'/>
    </div>
  </div>
</template>

<style scoped>
.main {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 1280px;
  height: 132px;
  border: 1px solid #D0D5DD;
  border-radius: 12px;
  margin-top: 36px;
}

.main__inner {
  display: flex;
  align-items: center;
  gap: 12px;
}
</style>
