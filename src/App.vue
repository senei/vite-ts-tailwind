<template>
  <div class="grid grid-cols-auto grid-rows-1 gap-1 absolute">
    <div @click="active = 0" ref="logoBox" 
      class="logo-box col-start-1">
      <div>logo |</div>
    </div>
    <div @click="active = (active == 1 ? -1 : 1)" :class="{'active': active == 1}" 
      ref="box-1" class="box box-1 col-start-2">
      <div class="flex-1 self-center">D1</div>
    </div>
    <div @click="active = (active == 2 ? -1 : 2)" :class="{'active': active == 2}"
      ref="box-2" class="box box-2 col-start-3">
      <div class="flex-1 self-center">D2</div>
    </div>
    <div @click="active = (active == 3 ? -1 : 3)" :class="{'active': active == 3}"
      ref="box-3" class="box box-3 col-start-4">
      <div class="flex-1 self-center">D3</div>
    </div>
    <div @click="active = (active == 4 ? -1 : 4)" :class="{'active': active == 4}"
      ref="box-4" class="box box-4 col-start-5">
      <div class="flex-1 self-center">D4</div>
    </div>
    <div @click="active = (active == 5 ? -1 : 5)" :class="{'active': active == 5}"
      ref="box-5" class="box box-5 col-start-6">
      <div class="flex-1 self-center">D5</div>
    </div>
    <div class="h-100 w-10 row-start-1 col-start-7"></div>
  </div>
</template>

<script lang="ts">
import { defineComponent,ref,reactive,watch,computed,onMounted } from 'vue'
import TWEEN from '@tweenjs/tween.js'

import HelloWorld from './components/HelloWorld.vue'

export default defineComponent({
  components: {
    HelloWorld,
  },
  setup() {
    const logoBox = ref(null);
    const active = ref(0);
     
    onMounted(() => {
    });

    watch(active, ( _new, _old)=>{
      console.info(_new, _old)      
    });
    
    return {
      logoBox, active
    };
  }
})
</script>

<style >
.grid-cols-auto {
  grid-auto-columns: min-content;
  bottom: 0.5rem;
}
.grid-cols-auto > div{
  text-align: center;
  transition: all 0.5s;
}
.grid-cols-auto > .h-100 {
  height: 100px; 
}
.grid-cols-auto > .logo-box {
  width: 216px;
  text-align: right;
  @apply flex items-center justify-end pr-1; 
  @apply border-r-4 border-gray-400;
}
.grid-cols-auto > .box {
  width: 100px;
  @apply flex items-center;
  @apply border border-gray-400 border-dashed;
}
.grid-cols-auto > .box.active {
  width: 540px;
  @apply mx-8;
}
</style>