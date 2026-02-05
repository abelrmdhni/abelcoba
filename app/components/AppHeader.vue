<script setup lang="ts">
const route = useRoute()
const isOpen = ref(false)

const navItems = [
  { label: 'Beranda', to: '/' },
  { label: 'C&C', to: '/connect-collaboration' },
  { label: 'BranovaAcademy', to: '/branova-academy' },
  { label: 'Brainova', to: '/brainova' }
]

const isItemActive = (path: string) => route.path === path
</script>

<template>
  <div>
    <UHeader class="bg-slate-900 border-b border-slate-800 py-6">
      <template #left>
        <div class="w-10" /> <!-- Spacer for balance -->
      </template>

      <!-- Desktop Navigation -->
      <nav class="hidden lg:flex items-center justify-center gap-2">
        <NuxtLink
          v-for="item in navItems"
          :key="item.to"
          :to="item.to"
          class="px-6 py-2.5 rounded-full text-sm font-medium transition-all duration-200"
          :class="[
            isItemActive(item.to)
              ? 'bg-amber-400 text-slate-900 font-semibold shadow-md'
              : 'text-white hover:text-gray-200 hover:bg-white/5'
          ]"
        >
          {{ item.label }}
        </NuxtLink>
      </nav>

      <template #right>
        <!-- Globe Icon (Decorative) -->
        <UButton
          icon="i-lucide-globe"
          color="white"
          variant="ghost"
          aria-label="Globe"
          class="hover:bg-white/10"
        />
      </template>

      <!-- Mobile Toggle -->
      <template #toggle>
        <UButton
          icon="i-lucide-menu"
          color="white"
          variant="ghost"
          @click="isOpen = true"
          aria-label="Menu"
          class="hover:bg-white/10"
        />
      </template>
    </UHeader>

    <!-- Mobile Navigation Drawer -->
    <UDrawer v-model:open="isOpen" direction="right">
      <template #content>
        <div class="flex flex-col h-full bg-slate-900 p-6 w-72">
          <div class="flex justify-end mb-8">
            <UButton
              icon="i-lucide-x"
              color="white"
              variant="ghost"
              @click="isOpen = false"
              aria-label="Close"
              class="hover:bg-white/10"
            />
          </div>
          <nav class="flex flex-col gap-4">
            <NuxtLink
              v-for="item in navItems"
              :key="item.to"
              :to="item.to"
              class="px-4 py-3 rounded-xl text-lg transition-colors duration-200"
              :class="[
                isItemActive(item.to)
                  ? 'bg-amber-400 text-slate-900 font-bold'
                  : 'text-gray-300 hover:text-white hover:bg-white/5'
              ]"
              @click="isOpen = false"
            >
              {{ item.label }}
            </NuxtLink>
          </nav>
        </div>
      </template>
    </UDrawer>
  </div>
</template>
