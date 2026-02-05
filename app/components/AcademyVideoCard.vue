<template>
  <div class="bg-white rounded-xl overflow-hidden shadow-sm hover:shadow-md transition-shadow">
    <!-- Video Thumbnail -->
    <div class="relative aspect-video bg-slate-200">
      <!-- Placeholder for video thumbnail -->
      <div class="absolute inset-0 flex items-center justify-center">
        <UIcon name="i-lucide-image" class="w-12 h-12 text-slate-400" />
      </div>
      <!-- Branova watermark -->
      <div class="absolute top-3 left-3 flex items-center gap-1 text-white text-xs font-medium">
        <UIcon name="i-lucide-sparkles" class="w-4 h-4" />
        <span>Branova</span>
      </div>
    </div>

    <!-- Content -->
    <div class="p-4">
      <!-- Title -->
      <h3 class="text-slate-900 font-bold text-sm mb-2 line-clamp-2 uppercase">
        {{ title }}
      </h3>

      <!-- Description -->
      <p class="text-slate-500 text-xs mb-3 line-clamp-2">
        {{ description }}
      </p>

      <!-- Stats Row -->
      <div class="flex items-center gap-4 text-xs text-slate-500 mb-4">
        <div class="flex items-center gap-1">
          <UIcon name="i-lucide-users" class="w-4 h-4" />
          <span>{{ views }}</span>
        </div>
        <div class="flex items-center gap-1">
          <UIcon name="i-lucide-star" class="w-4 h-4" />
          <span>{{ rating }}/5</span>
        </div>
        <div class="flex items-center gap-1">
          <UIcon name="i-lucide-tag" class="w-4 h-4" />
          <span :class="price === 'Gratis' ? 'text-green-600 font-medium' : ''">{{ price }}</span>
        </div>
      </div>

      <!-- Watch Button -->
      <UButton
        icon="i-lucide-play-circle"
        size="sm"
        class="bg-slate-800 hover:bg-slate-700 text-white text-xs font-bold w-full justify-center"
      >
        TONTON SEKARANG
      </UButton>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  title: string
  description: string
  views: string
  rating: string
  price: string
}>()
</script>
