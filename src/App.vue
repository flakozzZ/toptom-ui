<script setup lang="ts">
import { useI18n } from 'vue-i18n'
import StorybookHeader from '@/header/index.vue'
import ProgressBar from '@/components/progress-bar/index.vue'
import TooltipComponent from '@/components/tooltip/index.vue'

const i18n = useI18n()

console.log(i18n.t('test-message'))

i18n.locale.value = 'en'

console.log(i18n.t('test-message'))

const text = "Text"
</script>

<template>
  <main>
    <div class='container'>
      <storybook-header/>
      <progress-bar/>
      <div class='tooltip'>
        <tooltip-component :text='text'/>
        <tooltip-component :text='text'/>
        <tooltip-component :text='text'/>
        <tooltip-component :text='text'/>
      </div>
    </div>
  </main>
</template>

<style scoped lang='scss'>

.container {
  width: 100%;
  max-width: 1280px;
  margin: 0 auto;
}

.tooltip {
  display: flex;
  gap: 12px;
}


</style>
