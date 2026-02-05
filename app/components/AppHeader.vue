<script setup lang="ts">
const isOpen = ref(false)

const navItems = [
  { label: 'Beranda', to: '/' },
  { label: 'C&C', to: '/connect-collaboration' },
  { label: 'BranovaAcademy', to: '/branova-academy' },
  { label: 'Brainova', to: '/brainova' }
]
</script>

<template>
  <div>
    <UHeader class="bg-slate-900 border-b border-slate-800">
      <template #left>
        <!-- Placeholder for alignment -->
      </template>

      <!-- Desktop Navigation -->
      <UNavigationMenu 
        :items="navItems" 
        class="hidden lg:flex" 
        :ui="{ link: 'text-gray-300 hover:text-white' }"
      />

      <template #right>
        <!-- Globe Icon (Decorative) -->
        <UButton
          icon="i-lucide-globe"
          color="white"
          variant="ghost"
          aria-label="Globe"
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
        />
      </template>
    </UHeader>

    <!-- Mobile Navigation Drawer -->
    <UDrawer v-model:open="isOpen" direction="right">
      <template #content>
        <div class="flex flex-col h-full bg-slate-900 p-4 w-64">
          <div class="flex justify-end mb-4">
            <UButton
              icon="i-lucide-x"
              color="white"
              variant="ghost"
              @click="isOpen = false"
              aria-label="Close"
            />
          </div>
          <UNavigationMenu
            :items="navItems"
            orientation="vertical"
            class="flex-1"
            :ui="{ link: 'text-gray-300 hover:text-white text-lg py-3' }"
            @click="isOpen = false"
          />
        </div>
      </template>
    </UDrawer>
  </div>
</template>
