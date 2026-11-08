<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" :curCreamer :curSyrup />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
      <li>
        <template v-for="base in bases" :key='base.name'>
          <label>
            <input
              type="radio"
              name="base"
              :id="`r${base.id}`"
              :value="base.color"
              v-model="curBase"
            />
            {{base.name}}
          </label>
        </template>
      </li>
      <li>
        <template v-for="creamer in creamers" :key='creamer.name'>
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`r${creamer.id}`"
              :value="creamer.color"
              v-model="curCreamer"
            />
            {{creamer.name}}
          </label>
        </template>
      </li>
      <li>
        <template v-for="syrup in syrups" :key='syrup.name'>
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${syrup.id}`"
              :value="syrup.color"
              v-model="curSyrup"
            />
            {{syrup.name}}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";
import {bases, syrups, creamers} from "./stores/beverage";
import {curBase, curSyrup, curCreamer} from "./stores/beverage";

</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
