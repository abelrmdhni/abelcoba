<template>
  <aside class="w-64 bg-slate-100 min-h-screen p-6 flex flex-col">
    <!-- Logo Section -->
    <div class="mb-10">
      <div class="flex items-center gap-2 mb-1">
        <UIcon name="i-lucide-graduation-cap" class="w-8 h-8 text-slate-800" />
        <div>
          <h1 class="text-2xl font-bold text-slate-800 leading-none">Branova</h1>
          <h2 class="text-2xl font-bold text-amber-500 leading-none">Academy</h2>
        </div>
      </div>
      <p class="text-slate-600 text-sm mt-2 italic">Go Digital, Go Profit!</p>
    </div>

    <!-- Navigation Menu -->
    <nav class="flex flex-col gap-3">
      <button
        v-for="item in menuItems"
        :key="item.id"
        :class="[
          'flex items-center gap-3 px-4 py-3 rounded-lg text-left transition-colors',
          activeSection === item.id
            ? 'bg-slate-800 text-white'
            : 'text-slate-700 hover:bg-slate-200'
        ]"
        @click="activeSection = item.id"
      >
        <UIcon :name="item.icon" class="w-5 h-5" />
        <span class="font-medium">{{ item.label }}</span>
      </button>
    </nav>
  </aside>
</template>

<script setup lang="ts">
const activeSection = defineModel<string>({ default: 'mini-bootcamp' })

const menuItems = [
  { id: 'mini-bootcamp', label: 'Mini Bootcamp', icon: 'i-lucide-presentation' },
  { id: 'event-live', label: 'Event Live', icon: 'i-lucide-video' },
  { id: 'e-course', label: 'E-Course', icon: 'i-lucide-book-open' }
]
</script>
