<template>
  <div class="bg-white rounded-2xl border border-gray-200 p-6 flex gap-5 shadow-sm hover:shadow-md transition-shadow duration-200">
    <!-- Photo (Left) -->
    <div class="flex-shrink-0">
      <img 
        :src="photo" 
        :alt="name"
        class="w-[100px] h-[100px] object-cover rounded-xl bg-gray-100"
      />
    </div>

    <!-- Content Area (Middle & Right) -->
    <div class="flex-1 flex flex-col min-w-0">
      <!-- Header Section: Name/Info & Rating/Price -->
      <div class="flex justify-between items-start gap-4">
        <!-- Middle: Name, Badges, Age/Loc -->
        <div class="flex-1 min-w-0">
          <h3 class="text-xl font-bold text-slate-900 truncate">{{ name }}</h3>
          
          <!-- Expertise Badges -->
          <div class="flex flex-wrap gap-2 mt-2">
            <span 
              v-for="(expertise, index) in expertises" 
              :key="index"
              class="inline-flex items-center gap-1.5 px-3 py-1 bg-gray-100 rounded-full text-xs font-medium text-slate-700"
            >
              <span class="text-base">{{ expertise.icon }}</span>
              <span>{{ expertise.label }}</span>
            </span>
          </div>

          <!-- Age & Location -->
          <div class="flex items-center gap-4 mt-2 text-sm text-slate-500">
            <div class="flex items-center gap-1.5">
              <UIcon name="i-lucide-user" class="w-4 h-4 text-slate-400" />
              <span>{{ age }} Tahun</span>
            </div>
            <div class="flex items-center gap-1.5">
              <UIcon name="i-lucide-map-pin" class="w-4 h-4 text-slate-400" />
              <span>{{ location }}</span>
            </div>
          </div>
        </div>

        <!-- Right: Rating & Price -->
        <div class="flex flex-col items-end gap-1 flex-shrink-0">
          <div class="flex items-center gap-1.5">
            <UIcon name="i-lucide-star" class="w-4 h-4 text-amber-400 fill-amber-400" />
            <span class="text-sm font-bold text-slate-900">{{ rating }}</span>
          </div>
          <div class="flex items-center gap-1.5">
            <UIcon name="i-lucide-tag" class="w-4 h-4 text-slate-400" />
            <span class="text-sm font-semibold text-slate-900">{{ formattedPrice }}</span>
          </div>
        </div>
      </div>

      <!-- Description -->
      <p class="text-sm text-slate-600 mt-4 line-clamp-2 leading-relaxed">
        {{ description }}
      </p>

      <!-- Buttons (Bottom Right) -->
      <div class="flex items-center justify-end gap-3 mt-auto pt-4">
        <UButton 
          variant="outline" 
          size="sm"
          class="rounded-full border-slate-300 text-slate-700 hover:bg-slate-50 px-4"
        >
          Lihat Profil
        </UButton>
        <UButton 
          color="blue" 
          variant="solid" 
          size="sm"
          class="rounded-full bg-blue-500 hover:bg-blue-600 text-white px-5"
        >
          Kirim Pesan
        </UButton>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Expertise {
  icon: string
  label: string
}

interface Props {
  name: string
  photo: string
  expertises: Expertise[]
  age: number
  location: string
  description: string
  rating: number
  price: number
}

const props = defineProps<Props>()

const formattedPrice = computed(() => {
  return `Rp ${props.price.toLocaleString('id-ID')}`
})
</script>
