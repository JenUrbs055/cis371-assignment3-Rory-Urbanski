<template>
  <div class="syrup" :style="{'--stripe-color': syrupColor}"></div>
</template>

<script setup lang="ts">
import {ref} from 'vue';
import {curSyrup} from "../stores/beverage";

const syrupColor = ref(curSyrup);
</script>
<style lang="scss" scoped>

.syrup {
  transform: translateY(400%);
  background: repeating-linear-gradient(45deg,var(--stripe-color), var(--stripe-color) 10px,#e1cf95 10px, #e1cf95 20px);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
