<script lang='ts'>
export default {
  name: 'tooltip-component'
}
</script>

<template>
  <div class='tooltip'>
    <div class='tooltip__text'>
      {{ props.text }}
    </div>
    <div class='tooltip__inner' />
  </div>
</template>

<script setup lang='ts'>
interface Props {
  text: string,
}

const props = withDefaults(defineProps<Props>(), {})
</script>

<style scoped lang='scss'>
.tooltip {
  position: relative;
  width: 297px;
  height: 48px;
  border-radius: 12px;
  background: #0F0E14;
  text-align: center;
  padding: 15px 20px;
  color: #FFFFFF;

  &__text {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 1000;
  }

  &__inner {
    position: absolute;
    width: 27px;
    height: 27px;
    transform: rotate(-45deg) translate(-50%, -50%);
    background: #0F0E14;
    left: 52%;
    top: -10%;
  }
}


</style>
