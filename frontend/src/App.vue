<template>
  <div class="flex h-screen bg-gray-100">
    <!-- Sidebar -->
    <aside class="w-64 bg-gray-800 text-white">
      <div class="p-4">
        <h1 class="text-2xl font-bold mb-4">KK's Redis Cli</h1>
        <nav>
          <button
            v-for="route in routes"
            :key="route.path"
            @click="navigateTo(route.path)"
            class="block w-full text-left py-2 px-4 rounded transition duration-200 ease-in-out"
            :class="{ 'bg-gray-700': currentRoute === route.path }"
          >
            {{ route.name }}
          </button>
        </nav>
      </div>
    </aside>

    <!-- Main content -->
    <main class="flex-1 p-8">
      <router-view></router-view>
    </main>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import { useRouter, useRoute } from 'vue-router'

const router = useRouter()
const route = useRoute()

const routes = [
  { path: '/', name: '主页' },
]

const currentRoute = computed(() => route.path)

const navigateTo = (path) => {
  router.push(path)
}
</script>