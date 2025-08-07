<template>
  <div class="relative bg-white rounded-lg overflow-hidden shadow-lg group">
    <div class="relative">
      <img
        :src="image"
        alt="Chef image"
        class="w-full h-72 object-cover transition-transform duration-500 group-hover:-translate-y-2"
      />

      <!-- Wave SVG Shape -->
      <div class="absolute bottom-0 left-0 w-full overflow-hidden leading-[0]">
        <svg
          class="relative block w-full h-10"
          xmlns="http://www.w3.org/2000/svg"
          preserveAspectRatio="none"
          viewBox="0 0 1200 120"
        >
          <path
            d="M0,0V46.29c47.65,22.52,103.08,29,158,17.39C289.74,38.8,373.2-12.5,480,1.61s172,72.8,276,74.1c103.54,1.3,172-45.27,256-59.18C1081.63,3.61,1141.44,10,1200,27.35V0Z"
            class="fill-white"
          ></path>
        </svg>
      </div>

      <!-- Social Icons -->
      <div class="absolute top-4 right-4 flex flex-col items-center opacity-0 group-hover:opacity-100 transition-opacity">
        <a :href="facebook" target="_blank" class="mb-2 text-gray-700 hover:text-blue-600">
          <i class="fab fa-facebook-f"></i>
        </a>
        <a :href="twitter" target="_blank" class="mb-2 text-gray-700 hover:text-sky-400">
          <i class="fab fa-twitter"></i>
        </a>
        <a :href="linkedin" target="_blank" class="text-gray-700 hover:text-blue-700">
          <i class="fab fa-linkedin-in"></i>
        </a>
      </div>
    </div>

    <div class="p-6 text-center">
      <h3 class="text-lg font-bold text-gray-800">{{ name }}</h3>
      <p class="text-sm text-gray-500">{{ title }}</p>
      <p class="mt-2 text-sm text-gray-600">{{ description }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  name: String,
  title: String,
  description: String,
  image: String,
  facebook: String,
  twitter: String,
  linkedin: String
})
</script>

<style scoped>
.group:hover img {
  animation: float 3s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}
</style>
