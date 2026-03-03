<template>
  <div class="flex rounded-2xl shadow-xl p-8">
    <div class="flex flex-col gap-6 mt-6">
      <h1 class="flex items-center justify-center">Cafe Radar</h1>
      <section>
        <label class="text-xs">場所を選ぶ</label>
        <div class="flex items-center justify-center gap-4">
          <button class="cursor-pointer border border-gray-300 px-4 py-2 rounded hover:bg-gray-100 active:bg-gray-200 w-50 h-14">
            現在地
          </button>
          <button class="cursor-pointer border border-gray-300 px-4 py-2 rounded hover:bg-gray-100 active:bg-gray-200 w-50 h-14">
            駅名で指定
          </button>
        </div>
        <div class="mt-4">
          <input 
            class="border border-gray-300 px-4 py-2 rounded w-full"
            type="text" 
            placeholder="例：渋谷駅、新宿駅..." 
            autocomplete="off" 
          >
        </div>
      </section>
      <section>
        <label class="text-xs">探す範囲</label>
        <div class="flex items-center justify-center gap-1">
          <button class="cursor-pointer border border-gray-300 px-4 py-2 rounded hover:bg-gray-100 active:bg-gray-200 w-34 h-14" >すぐそこ</button>
          <button class="cursor-pointer border border-gray-300 px-4 py-2 rounded hover:bg-gray-100 active:bg-gray-200 w-34 h-14">ちょうどいい</button>
          <button class="cursor-pointer border border-gray-300 px-4 py-2 rounded hover:bg-gray-100 active:bg-gray-200 w-34 h-14">冒険したい</button>
        </div>
      </section>
      <section class="flex items-center justify-center">
        <button
          class="cursor-pointer border border-gray-300 px-4 py-2 rounded hover:bg-gray-100 active:bg-gray-200 w-104 h-14"
          @click="isModalOpen = true"
        >ここいけ</button>
      </section>
      <div class="flex items-center justify-center mt-6">
        <p>Copyright © 2026 Cafe Radar All Rights Reserved.</p>
      </div>
    </div>
  </div>
  <CafeModal :is-open="isModalOpen" @close="isModalOpen = false" />

</template>

<script setup lang="js">
import { ref } from 'vue'
import CafeModal from '~/components/CafeModal.vue'

const isModalOpen = ref(false)
</script>

<style lang="scss" scoped>

</style>