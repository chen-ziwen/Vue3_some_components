<template>
   <div class="row-banner-li"></div>
</template>

<script lang="ts" setup>
import { computed } from 'vue';
interface RowBannerLi {
    theme:String
}
const props =  defineProps<RowBannerLi>()
const src = computed(()=>`url(/assets/images/common/RowBanner/${props.theme}2.png)`)
</script>

<style lang="scss" scoped>
.row-banner-li {
    display: inline-block;
    white-space: nowrap;
    height: 80px;
    width: 52px;
    background: v-bind(src) no-repeat;
    background-size: 52px 80px;
    vertical-align: middle;
}
</style>