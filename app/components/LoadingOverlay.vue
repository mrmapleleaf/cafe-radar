<template>
  <div
    v-if="isLoading"
    class="fixed inset-0 z-50 flex flex-col items-center justify-center bg-black/50"
  >
    <div class="w-12 h-12 border-4 border-white/30 border-t-white rounded-full animate-spin" />
    <p class="mt-4 text-white text-sm">カフェを探しています...</p>
  </div>
</template>

<script setup lang="js">
defineProps({
  isLoading: {
    type: Boolean,
    required: true,
  },
})
</script>