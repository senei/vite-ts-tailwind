<template>
  <div class="grid grid-cols-7 grid-rows-3 gap-1 w-full ml-4" 
    :style="{'grid-template-columns': gtcStyle}">
    <div ref="logoBox" style=" height: 100px; " 
         class="bg-yellow-100 row-start-2 col-start-1 col-span-2">
      logo
    </div>
    <div @click="active = 5" class="bg-green-300 row-start-2 col-start-7">D5</div>
    <!-- <div class="bg-green-200 row-start-3 col-start-2">M5</div> -->
    <div @click="active = 4" class="bg-green-300 row-start-2 col-start-6">D4</div>
    <!-- <div class="bg-green-200 row-start-1 col-start-2">M4</div> -->
    <div @click="active = 3" class="bg-green-300 row-start-2 col-start-5">D3</div>
    <!-- <div class="bg-green-200 row-start-3 col-start-3">M3</div> -->
    <div @click="active = 2" class="bg-green-300 row-start-2 col-start-4">D2</div>
    <!-- <div class="bg-green-200 row-start-1 col-start-3">M2</div> -->
    <div @click="active = 1" class="bg-green-100 row-start-2 col-start-3">D1</div>

    <div class="row-start-2 col-start-8"></div>

  </div>
</template>

<script lang="ts">
import { defineComponent,ref,reactive,watch,computed,onMounted } from 'vue'

import HelloWorld from './components/HelloWorld.vue'

export default defineComponent({
  components: {
    HelloWorld,
  },
  setup() {
    const logoBox = ref(null);
    const active = ref(0);
    const gtc = reactive([100,100,200,120,110,100]);
    const gtcStyle = computed(() => `${gtc[0]}px ${gtc[0]}px ${gtc[1]}px ${gtc[2]}px ${gtc[3]}px ${gtc[4]}px ${gtc[5]}px ${gtc[0]}px`);
    
    onMounted(() => {
      console.log(logoBox.value.getBoundingClientRect());
    });

    watch(active, ( _new, _old)=>{
      gtc[_old] = 100;
      gtc[_new] = 540;
    });

    return {
      logoBox, gtc, gtcStyle,active
    };
  }
})
</script>

<style>
.grid-cols-7 {
  transition: 
    grid-template-columns ease-in-out 500ms, 
    grid-template-row     ease-in-out 500ms;
}
</style>