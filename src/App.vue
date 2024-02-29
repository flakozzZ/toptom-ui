<script setup lang="ts">
import { useI18n } from 'vue-i18n'
import StorybookHeader from '@/header/index.vue'
import ProgressBar from '@/components/progress-bar/index.vue'

const i18n = useI18n()

console.log(i18n.t('test-message'))

i18n.locale.value = 'en'

console.log(i18n.t('test-message'))
</script>

<template>
  <main>
    <div class='container'>
      <storybook-header/>
      <progress-bar/>
    </div>
  </main>
</template>

<style scoped lang='scss'>

.container {
  width: 100%;
  max-width: 1280px;
  margin: 0 auto;
}


</style>
