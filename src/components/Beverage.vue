<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Base v-if="curCreamer==='transparent' && curSyrup==='#c6c6c6'"/>
        <Creamer v-else/>
      </template>
      <template v-slot:mid>
        <Base v-if="curSyrup==='#c6c6c6'"/>
        <Syrup v-else />
      </template>
      <template v-slot:bottom>
        <Base />
      </template>
    </Contents>
  </Mug>
</template>
<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

type Props = {
  isIced: boolean;
  curCreamer: string;
  curSyrup: string;
};
defineProps<Props>();



</script>
