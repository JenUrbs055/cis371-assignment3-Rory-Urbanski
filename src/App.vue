<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
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
        <template v-for="base in bases" :key='base.id'>
          <label>
            <input
              type="radio"
              name="base"
              :id="`r${base}`"
              :value="base"
            />
            {{base.name}}
          </label>
        </template>
      </li>
      <li>
        <template v-for="creamer in creamers" :key='creamer.id'>
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`r${creamer}`"
              :value="creamer"
            />
            {{creamer.name}}
          </label>
        </template>
      </li>
      <li>
        <template v-for="syrup in syrups" :key='syrup.id'>
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${syrup}`"
              :value="syrup"
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
