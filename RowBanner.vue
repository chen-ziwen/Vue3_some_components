<template>
  <div class="row-banner">
     <div class="border style flex">
         <slot></slot>
     </div>
  </div>
</template>

<script lang="ts" setup>
 import { computed } from 'vue';
 interface RowBanner {
     theme : string
 }
 const props = defineProps<RowBanner>()
 const  src = computed(()=>`url(/assets/images/common/RowBanner/${props.theme}.png)`)
</script>

<style lang="scss" scoped>
.row-banner {
 display: inline-block;
.border {
 border-image-source: v-bind(src);
 border-image-slice:0 35 0 35 fill;
 border-image-width:0px 35px 0px 35px;
 border-image-outset:0px 35px 0px 35px;
 border-image-repeat:round;
}
.style {
 display: inline-block;
 white-space: nowrap;
 width: auto;
 height: 80px;
 font-size: 24px;
}
.flex {
  display: flex;
  justify-content: center;
  align-items: center;
}
}
</style>