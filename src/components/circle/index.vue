<script lang='ts'>
export default {
  name: "circle-component"
}
</script>

<template>
  <template v-for='(item, index) in items' :key='item.key'>
      <line-component :is-active='item.isActive' v-if='index > 0'/>
      <div class='circle-container'>
        <div class='outer-circle' @mouseover='showTooltip(index)' @mouseout='hideTooltip' :class='{active: item.isActive}'>
          <div class='inner-circle' :class='{active: item.isActive}'></div>
        </div>
        <div class='circle-text' :class='{active: item.isActive}'>{{ item.text }}</div>
      </div>
    <div class='tooltip'>
      <tooltip-component v-if='tooltipIndex == index' :text='item.tooltipText'/>
    </div>
  </template>
</template>

<script setup lang='ts'>
import LineComponent from '@/components/line/index.vue'
import TooltipComponent from '@/components/tooltip/index.vue'
import { ref } from 'vue'


interface IItem {
  key: string,
  text: string,
  tooltipText: string,
  isActive: boolean,
}

interface Props {
  items: IItem[]
}

withDefaults(defineProps<Props>(), {})

const tooltipIndex = ref<number | null>(null)


const showTooltip =  (index: number) => {
  tooltipIndex.value = index
}

const hideTooltip = () => {
  tooltipIndex.value = null
}

</script>




<style scoped lang='scss'>

.circle-container {
  display: flex;
  align-items: center;
  gap: 12px;
  position: relative;
}

.outer-circle {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #F5F6F8;
  position: relative;
  overflow: hidden;
  z-index: 1;
  &.active {
    background: #FA4D1E;
  }
}

.inner-circle {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  position: absolute;
  background: #D0D5DD;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  &.active {
    background: #FFFFFF;
  }
}

.circle-text {
  width: 200px;
  text-align: center;
  position: absolute;
  color: #8B91A9;
  top: calc(50% + 20px);
  transform: translateX(-50%);
  left: 7%;
  font-size: 14px;
  z-index: 0;
  line-height: 20px;
  font-weight: 500;
  &.active {
    color: #0F0E14;
  }
}

.tooltip {
  position: absolute;
  top: calc(50% + 40px); /* Adjust the value based on your design */
  left: 50%;
  transform: translateX(-50%);
}
</style>

