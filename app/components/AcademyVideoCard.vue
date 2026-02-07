<template>
  <div class="group bg-white rounded-2xl overflow-hidden shadow-lg hover:shadow-xl transition-all duration-300 hover:-translate-y-1 border border-slate-100 flex flex-col h-full cursor-pointer">
    <!-- Thumbnail Section -->
    <div class="relative h-48 bg-slate-900 overflow-hidden">
      <!-- Background Image -->
      <img 
        src="https://images.unsplash.com/photo-1556761175-5973dc0f32e7?q=80&w=2664&auto=format&fit=crop" 
        alt="Thumbnail" 
        class="absolute inset-0 w-full h-full object-cover opacity-60 group-hover:scale-105 transition-transform duration-700 ease-out"
      />
      
      <!-- Gradient Overlay -->
      <div class="absolute inset-0 bg-gradient-to-t from-slate-900/90 via-slate-900/50 to-slate-900/30"></div>

      <!-- Branova Logo Top Left -->
      <div class="absolute top-4 left-4 flex items-center gap-1.5 z-20">
        <div class="bg-white/10 backdrop-blur-md p-1.5 rounded-lg border border-white/10">
          <UIcon name="i-lucide-sparkles" class="w-3.5 h-3.5 text-yellow-400" />
        </div>
        <span class="text-white/95 text-xs font-bold tracking-wide shadow-sm">Branova</span>
      </div>

      <!-- Thumbnail Content Center -->
      <div class="absolute inset-0 flex flex-col items-center justify-center p-6 text-center z-10">
        <!-- Badge -->
        <div class="inline-flex items-center justify-center px-3 py-1 mb-2 bg-gradient-to-r from-orange-500 to-red-600 rounded-full shadow-lg transform -rotate-2 border border-white/10">
          <span class="text-[10px] font-black text-white uppercase tracking-widest leading-none">Dari Lokal Jadi Viral</span>
        </div>
        
        <!-- Subtitle -->
        <p class="text-white/90 text-[10px] font-medium leading-relaxed max-w-[200px] drop-shadow-md tracking-wide">
          STRATEGI BRANDING & MARKETING DIGITAL UNTUK UMKM
        </p>
      </div>
    </div>

    <!-- Content Section -->
    <div class="p-5 flex flex-col flex-grow bg-white relative z-20">
      <!-- Title -->
      <h3 class="text-slate-900 font-extrabold text-sm leading-snug uppercase mb-2 line-clamp-2 tracking-tight group-hover:text-slate-700 transition-colors">
        {{ title }}
      </h3>

      <!-- Description -->
      <p class="text-slate-500 text-xs leading-relaxed mb-5 line-clamp-2 flex-grow font-medium">
        {{ description }}
      </p>

      <!-- Stats Row -->
      <div class="flex items-center justify-between text-xs text-slate-500 mb-5 pt-4 border-t border-slate-100">
        <div class="flex items-center gap-1.5 group/stat hover:text-slate-700 transition-colors">
          <UIcon name="i-lucide-users" class="w-3.5 h-3.5" />
          <span class="font-semibold">{{ views }}</span>
        </div>
        <div class="flex items-center gap-1.5 group/stat hover:text-slate-700 transition-colors">
          <UIcon name="i-lucide-star" class="w-3.5 h-3.5 text-yellow-500 fill-yellow-500" />
          <span class="font-semibold">{{ rating }}/5</span>
        </div>
        <div class="flex items-center gap-1.5 group/stat">
          <UIcon name="i-lucide-tag" class="w-3.5 h-3.5 text-slate-400" />
          <span :class="price === 'Gratis' ? 'text-emerald-600 font-bold bg-emerald-50 px-2 py-0.5 rounded-full border border-emerald-100' : 'font-semibold text-slate-700'">
            {{ price }}
          </span>
        </div>
      </div>

      <!-- Watch Button -->
      <button class="w-full bg-slate-800 hover:bg-slate-900 text-white text-xs font-bold py-3 px-4 rounded-xl flex items-center justify-center gap-2 transition-all duration-300 group/btn shadow-md hover:shadow-lg hover:scale-[1.02]">
        <span class="tracking-wider">TONTON SEKARANG</span>
        <UIcon name="i-lucide-play-circle" class="w-4 h-4 group-hover/btn:translate-x-0.5 transition-transform" />
      </button>
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
