<template>
  <div class="flex h-screen">
    <!-- Main Content -->
    <div class="flex-1 p-4">
      <div class="bg-white rounded-lg shadow-md h-full">
        <div class="p-4 space-y-4">
          <div class="text-sm text-gray-600">
            这里输入redis命令
          </div>
          <textarea
            v-model="command"
            class="w-full min-h-[200px] p-2 border rounded-md font-mono resize-none focus:outline-none focus:ring-2 focus:ring-[#F47373] focus:border-transparent"
            placeholder="Enter your Redis command here..."
          ></textarea>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script setup>
import { ref } from 'vue'
const command = ref('')
</script>

<style scoped>
/* Add any component-specific styles here if needed */
</style>