<template>
  <div class="flex rounded-2xl shadow-xl p-8">
    <div class="flex flex-col gap-6 mt-6">
      <h1 class="flex items-center justify-center">☕️ココイケ</h1>
      <section>
        <div class="pb-2">
          <label class="text-xs">どこから探す</label>
        </div>
        <div class="flex items-center justify-center gap-1">
          <button
            :class="[
              'cursor-pointer border px-4 py-2 rounded w-52 h-14',
              isInputVisible === false
                ? 'border-blue-500 bg-blue-50 text-blue-700'
                : 'border-gray-300 hover:bg-gray-100 active:bg-gray-200'
            ]"
            @click="activateStationInput(false)"
          >
            現在地
          </button>
          <button
            :class="[
              'cursor-pointer border px-4 py-2 rounded w-52 h-14',
              isInputVisible === true
                ? 'border-blue-500 bg-blue-50 text-blue-700'
                : 'border-gray-300 hover:bg-gray-100 active:bg-gray-200'
            ]"
            @click="activateStationInput(true)"
          >
            駅名で指定
          </button>
        </div>
        <div class="mt-4" v-if="isInputVisible">
          <input 
            class="border border-gray-300 px-4 py-2 rounded w-full"
            type="text" 
            placeholder="例：渋谷駅、新宿駅..." 
            autocomplete="off" 
          >
        </div>
      </section>
      <section>
        <div class="pb-2">
            <label class="text-xs">探す範囲</label>
        </div>
        <div class="flex items-center justify-center gap-1">
          <button 
            :class="[
              'cursor-pointer border px-4 py-2 rounded w-34 h-18',
              selectedRange === 0
                ? 'border-blue-500 bg-blue-50 text-blue-700'
                : 'border-gray-300 hover:bg-gray-100 active:bg-gray-200'
            ]"
            @click="activateRangeButton(0)"
          >
            すぐそこ
            500m
          </button>
          <button
            :class="[
              'cursor-pointer border px-4 py-2 rounded w-34 h-18',
              selectedRange === 1
                ? 'border-blue-500 bg-blue-50 text-blue-700'
                : 'border-gray-300 hover:bg-gray-100 active:bg-gray-200'
            ]"
            @click="activateRangeButton(1)"
          >
            ちょうどいい
            1km
          </button>
          <button
            :class="[
              'cursor-pointer border px-4 py-2 rounded w-34 h-18',
              selectedRange === 2
                ? 'border-blue-500 bg-blue-50 text-blue-700'
                : 'border-gray-300 hover:bg-gray-100 active:bg-gray-200'
            ]"
            @click="activateRangeButton(2)"
          >
            冒険したい
            3km
          </button>
        </div>
      </section>
      <section class="flex items-center justify-center">
        <button
          class="cursor-pointer border border-gray-300 px-4 py-2 rounded hover:bg-gray-100 active:bg-gray-200 w-104 h-14"
          @click="isModalOpen = true"
        >ココイケ</button>
      </section>
      <div class="flex items-center justify-center mt-6">
        <p>Copyright © 2026 ココイケ All Rights Reserved.</p>
      </div>
    </div>
  </div>
  <CafeModal :is-open="isModalOpen" @close="isModalOpen = false" />

</template>

<script setup lang="js">
import { ref } from 'vue'
import CafeModal from '~/components/CafeModal.vue'

const isModalOpen = ref(false)
const isInputVisible = ref(false)
const selectedRange = ref(1)

// 駅名入力の表示・非表示を切り替える関数
function activateStationInput(flg) {
  isInputVisible.value = flg
}

// 探索距離を選択するボタン
// 0: すぐそこ, 1: ちょうどいい, 2: 冒険したい
function activateRangeButton(index) {
  selectedRange.value = index
  console.log('Selected range index:', index)
}

</script>

<style lang="scss" scoped>

</style>