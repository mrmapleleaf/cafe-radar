<template>
  <div
    v-if="isOpen"
    class="fixed inset-0 z-50 flex items-center justify-center"
  >
    <!-- オーバーレイ -->
    <div
      class="absolute inset-0 bg-black/50"
      @click="$emit('close')"
    />

    <!-- モーダル本体 -->
    <div class="relative bg-white rounded-2xl shadow-xl w-full max-w-md mx-4 p-6">
      <button
        class="absolute top-4 right-4 cursor-pointer text-gray-400 hover:text-gray-600"
        @click="$emit('close')"
      >
        ✕
      </button>

      <h2 class="text-xl font-bold text-center mb-4">おすすめのカフェ</h2>

      <div class="flex flex-col gap-4">
        <div class="border border-gray-200 rounded-xl p-4">
          <p class="font-semibold">カフェ名がここに表示されます</p>
          <p class="text-sm text-gray-500 mt-1">住所・距離などの情報</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="js">
defineProps({
  isOpen: {
    type: Boolean,
    required: true,
  },
})

defineEmits(['close'])
</script>
