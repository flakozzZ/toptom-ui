<script lang='ts'>
export default {
  name: 'line-component'
}
</script>

<template>
  <div class='line' :class='{active: props.isActive}'>
  </div>
</template>

<script setup lang='ts'>
interface Props {
  isActive?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  isActive: false
})
</script>

<style scoped>
.line {
  width: 153px;
  height: 4px;
  background: #D0D5DD;
  border-radius: 10px;
  &.active {
    background: #FA4D1E;
  }
}
</style>
