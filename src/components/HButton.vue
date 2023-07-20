<template>
  <button class="button button-custom bg-gradient" :class="`shape-${shape} size-${size}`" :style="{ backgroundColor: color }" :disabled="disabled" :loading="loading">
    <slot v-if="!loading"></slot>
    <div v-else>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="h-[40px] animate-spin"><title>loading</title><path d="M12,4V2A10,10 0 0,0 2,12H4A8,8 0 0,1 12,4Z" /></svg>
    </div>
  </button>
</template>

<script setup>
import {ref} from 'vue'

const props = defineProps(['color', 'shape', 'size', 'disabled', 'loading'])
</script>

<style>
.button{
  @apply min-h-[32px] min-w-[60px] flex justify-center items-center
}
.button-custom{
  @apply rounded border-[2px] border-[#212529] text-[#212529] shadow-[0_5px_0px_rgba(33,37,41,1)] transition-none ease-linear relative
}

.button-custom:active{
  @apply shadow-none top-[5px]
}

.button-custom:hover{
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.50), rgba(255, 255, 255, 0.3));
}

.button-custom:disabled{
  @apply border-[#525252] text-[#525252] shadow-[#525252] !bg-slate-300 pointer-events-none
}

.shape-rounded{
  @apply rounded-full
}

.shape-box{
  @apply rounded-none
}

.bg-gradient{
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.30), rgba(255, 255, 255, 0));
}

.size-normal{
  @apply min-h-[40px] min-w-[120px] w-fit text-[14px] px-2 py-1
}
.size-medium{
  @apply min-h-[60px] min-w-[220px] w-fit text-[20px] px-4 py-2
}
.size-big{
  @apply min-h-[80px] w-[400px] text-[30px] px-6 py-3
}
</style>