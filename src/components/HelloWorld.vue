<template>
  <div ref="elem" class="px-8 prose">
    <h1>{{ msg }}</h1>
    <button class="px-3 py-2 border border-gray-300 rounded-md shadow" @click="count++">
      count is: {{ count }}
    </button>
    <p>{{ win }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, toRef, ref } from 'vue'
import { useEventListener } from '@vueuse/core'

import { globalState } from '../store'

export default defineComponent({
  props: {
    msg: String,
  },

  setup() {
    const el = ref(null)
    const reText = ref('')

    useEventListener(window, 'resize', () => { 
      const { innerWidth, innerHeight } = window
      reText.value = ` - in_width: ${innerWidth}, in_height: ${innerHeight}`
    })


    return {
      win: reText,
      elem: el,
      count: toRef(globalState, 'count'),
    }
  },
})
</script>
