<template>
  <div>
    <div class="w-full flex justify-center flex-col gap-10 py-20 px-10">
      <h-button :color="color" :shape="shape" :size="size" :disabled="disabled" :loading="loading" @click="text = 'Clicked!'">{{ text }}</h-button>
      <hr>
      <div>
        <div class="flex flex-col mb-4">
          <label class="text-sm mb-1">Color</label>
          <input type="color" class="border rounded w-full" v-model="color">
        </div>
        <div class="flex flex-col mb-4">
          <label class="text-sm mb-1">Shape</label>
          <select v-model="shape" class="p-2 border rounded">
            <option value="rounded">Rounded</option>
            <option value="box">Box</option>
          </select>
        </div>
        <div class="flex flex-col mb-4">
          <label class="text-sm mb-1">Size</label>
          <select v-model="size" class="p-2 border rounded">
            <option value="normal">Normal</option>
            <option value="medium">Medium</option>
            <option value="big">Big</option>
          </select>
        </div>
        <div class="flex flex-col items-start mb-4">
          <label class="text-sm mb-1">Disabled</label>
          <input type="checkbox" v-model="disabled">
        </div>
        <div class="flex flex-col items-start">
          <label class="text-sm mb-1">Loading</label>
          <input type="checkbox" v-model="loading">
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import HButton from './components/HButton.vue'
const text = ref('Hello World!')
const color = ref('#009aa7')
const shape = ref('rounded')
const size = ref('normal')
const disabled = ref(false)
const loading = ref(false)
</script>

<style>
</style>