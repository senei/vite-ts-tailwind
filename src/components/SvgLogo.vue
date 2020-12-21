<template>
  <svg class="logo" width="304px" height="304px" data-size="304x304" style="margin: auto;">
    <symbol id="_s" width="64" height="52" viewBox="0 0 62 52">
      <path d="M61.139 15.344L61.139 0 31.861 0 31.861 15.344z" />
      <path
        d="M48.798 52L61.139 36.641 61.139 18.783 14.508 18.783 17.522 14.804 29.015 14.804 29.015 0 12.152 0 0 15.452 0 26.648 14.319 26.648 19.5 33.217 46.631 33.217 43.617 37.196 32.03 37.196 32.03 52z"
      />
      <path d="M29.278 52L29.278 36.78 17.871 36.78 12.167 29.836 0 29.836 0 52z" />
    </symbol>
    <symbol id="_e" width="56" height="52" viewBox="0 0 56 52">
      <path
        d="M17.303 52L17.303 37.196 11.781 30.441 11.781 14.804 26.231 14.804 26.231 0 0 0 0 52z"
      />
      <path d="M55 15.344L55 0 29.615 0 29.615 15.344z" />
      <path d="M51.615 32.393L51.615 18.754 15.231 18.754 15.231 27.235 19.644 32.393z" />
      <path d="M55 52L55 36.656 20.308 36.656 20.308 52z" />
    </symbol>
    <symbol id="_n" viewBox="0 0 63 52" width="63" height="52">
      <path d="M17.29 52L17.29 37.196 11.772 30.441 11.772 0 0 0 0 52z" />
      <path
        d="M61.381 52L61.381 15.359 49.2 0 15.561 0 15.561 14.804 43.859 14.804 49.293 21.559 49.293 52z"
      />
    </symbol>
    <symbol id="_i" viewBox="0 0 18 52" width="18" height="52">
      <path d="M16.15 52L16.15 37.196 10.996 30.441 10.996 0 0 0 0 52z" />
    </symbol>
    <g class="senei" fill-rule="nonzero" ref="seneiRef" style="transform: translate(18px, 125px);">
      <use
        xlink:href="#_s"
        class="_s"
        ref="sRef"
        @click="getCssFromSvg"
        style="transform: translate(0, 0);"
      ></use>
      <use xlink:href="#_e" class="_e" ref="eRef" style="transform: translate(66px, 0px);"></use>
      <use xlink:href="#_n" class="_n" ref="nRef" style="transform: translate(125px, 0);"></use>
      <g class="_ei" ref="eiRef" style="transform: translate(191px, 0px);">
        <use xlink:href="#_e"></use>
        <use xlink:href="#_i" style="transform: translate(59px, 0px);"></use>
      </g>
    </g>
  </svg>
</template>
<script lang="ts">
import { defineComponent, toRef, ref } from 'vue'
export default defineComponent({
  props: {
    msg: String,
  },

  setup() {
    const seneiRef = ref(null),
      sRef = ref(null),
      eRef = ref(null),
      nRef = ref(null),
      eiRef = ref(null)
    const getCssFromSvg = () => {
      console.log(
        '.senei {' + seneiRef.value.getAttribute('style') + '}\n',
        '.senei .s {' + sRef.value.getAttribute('style') + '}\n',
        '.senei .e {' + eRef.value.getAttribute('style') + '}\n',
        '.senei .n {' + nRef.value.getAttribute('style') + '}\n',
        '.senei .ei {' + eiRef.value.getAttribute('style') + '}\n\n'
      )
    }

    return { getCssFromSvg, seneiRef, sRef, eRef, nRef, eiRef }
  },
})
</script>
<style>
svg.logo {
  overflow: visible;
  border: 1px solid black;
}
.senei.horisontal {
  width: 266px;
  height: 52px;
  transform: translate(18px, 125px);
}
.senei.horisontal .s {
  transform: translate(0px, 0px);
}
.senei.horisontal .e {
  transform: translate(66px, 0px);
}
.senei.horisontal .n {
  transform: translate(125px, 0px);
}
.senei.horisontal .ei {
  transform: translate(191px, 0px);
}
/**/
.senei.vertical {
  width: 75px;
  height: 220px;
  transform: translate(18px, 42px);
}
.senei.vertical .s {
  transform: translate(0px, 0px);
}
.senei.vertical .e {
  transform: translate(0px, 55px);
}
.senei.vertical .n {
  transform: translate(0px, 110px);
}
.senei.vertical .ei {
  transform: translate(0, 165px);
}
/*box*/
.senei.sqr {
  transform: translate(18px, 125px);
}
.senei.sqr .s {
  transform: translate(0px, 0px);
}
.senei.sqr .e {
  transform: translate(66px, 0px);
}
.senei.sqr .n {
  transform: translate(1px, 56px);
}
.senei.sqr .ei {
  transform: translate(66px, 56px);
}
</style>
