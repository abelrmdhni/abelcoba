<template>
  <div>
    <CCHeader />
    <div class="py-8 bg-slate-50 min-h-screen">
      <UContainer>
      <!-- Header Section -->
      <div class="flex items-center justify-between mb-6">
        <h1 class="text-2xl font-bold text-slate-900">Desain Logo Minimalis</h1>
        <NuxtLink to="#" class="flex items-center text-slate-600 hover:text-slate-900 font-medium text-sm transition-colors">
          Lihat semua
          <UIcon name="i-lucide-arrow-right" class="w-4 h-4 ml-1" />
        </NuxtLink>
      </div>

      <!-- Service Cards Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div v-for="(service, index) in services" :key="index" class="group cursor-pointer">
          <!-- Card Image -->
          <div class="relative aspect-video rounded-xl overflow-hidden mb-3">
            <img 
              :src="service.image" 
              :alt="service.description"
              class="w-full h-full object-cover transition-transform duration-300 group-hover:scale-105"
            />
          </div>

          <!-- Seller Info -->
          <div class="flex items-center mb-2">
            <UAvatar 
              :src="service.avatar" 
              :alt="service.seller"
              size="xs"
              class="mr-2"
            />
            <div class="text-sm">
              <span class="text-slate-500">Ad by</span>
              <span class="font-semibold text-slate-900 ml-1">{{ service.seller }}</span>
            </div>
          </div>

          <!-- Description -->
          <h3 class="text-slate-700 hover:text-slate-900 leading-snug mb-2 line-clamp-2 min-h-[2.5rem]">
            {{ service.description }}
          </h3>

          <!-- Rating -->
          <div class="flex items-center mb-2">
            <UIcon name="i-lucide-star" class="w-4 h-4 text-blue-500 fill-current" />
            <span class="font-bold text-slate-900 ml-1">{{ service.rating }}</span>
            <span class="text-slate-500 text-sm ml-1">({{ service.reviews }})</span>
          </div>

          <!-- Price -->
          <div class="text-slate-900 font-bold">
            Mulai harga Rp.{{ service.price }}
          </div>
        </div>
      </div>
    </UContainer>
    </div>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: 'Desain Logo Minimalis - Branova'
})

const services = [
  {
    image: 'https://placehold.co/600x338/e2e8f0/1e293b?text=Organic+Logo',
    avatar: 'https://placehold.co/100x100/3b82f6/ffffff?text=EV',
    seller: 'Ebel Vigra',
    description: 'Saya akan membuat desain logo yang bersih dan minimal',
    rating: '5.0',
    reviews: '2K+',
    price: '20.000'
  },
  {
    image: 'https://placehold.co/600x338/e2e8f0/1e293b?text=Coffee+Logo',
    avatar: 'https://placehold.co/100x100/10b981/ffffff?text=SA',
    seller: 'Syaban A.',
    description: 'Saya akan merancang logo minimalis Anda',
    rating: '4.9',
    reviews: '827',
    price: '40.000'
  },
  {
    image: 'https://placehold.co/600x338/e2e8f0/1e293b?text=Eco+Logo',
    avatar: 'https://placehold.co/100x100/f59e0b/ffffff?text=DS',
    seller: 'Daniel S.',
    description: 'Saya akan membuat logo minimal dan papan merek',
    rating: '5.0',
    reviews: '1K+',
    price: '32.000'
  }
]
</script>
