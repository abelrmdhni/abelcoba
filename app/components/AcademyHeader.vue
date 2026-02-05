<template>
  <header class="flex items-center justify-between py-4 px-6 bg-white">
    <!-- Search Bar -->
    <div class="flex-1 max-w-2xl">
      <UInput
        placeholder="Apa yang kamu cari"
        size="lg"
        variant="outline"
        :ui="{
          root: 'w-full',
          base: 'rounded-full border-2 border-slate-800 focus:ring-slate-800'
        }"
      >
        <template #leading>
          <UIcon name="i-lucide-sliders-horizontal" class="w-5 h-5 text-slate-600" />
        </template>
        <template #trailing>
          <UIcon name="i-lucide-search" class="w-5 h-5 text-slate-600" />
        </template>
      </UInput>
    </div>

    <!-- Action Icons -->
    <div class="flex items-center gap-2 ml-6">
      <UButton
        icon="i-lucide-bell"
        color="neutral"
        variant="ghost"
        size="lg"
        class="text-slate-800"
        aria-label="Notifications"
      />
      <UButton
        icon="i-lucide-shopping-cart"
        color="neutral"
        variant="ghost"
        size="lg"
        class="text-slate-800"
        aria-label="Cart"
      />
      <UButton
        icon="i-lucide-heart"
        color="neutral"
        variant="ghost"
        size="lg"
        class="text-slate-800"
        aria-label="Favorites"
      />
      <UButton
        icon="i-lucide-circle-user"
        color="neutral"
        variant="ghost"
        size="lg"
        class="text-slate-800"
        aria-label="Profile"
      />
    </div>
  </header>
</template>

<script setup lang="ts">
</script>
