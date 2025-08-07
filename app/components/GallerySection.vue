<template>
  <section class="gallery-section" id="GallerySection">
    <h5 class="text-sm text-center text-gray-400 tracking-widest uppercase">Gallery</h5>
    <h2 class="text-center text-3xl font-light">
      Check <span class="text-red-600">Our Gallery</span>
    </h2>

    <div class="slideshow">
      <button @click="prevSlide" class="nav-button">‹</button>

      <div class="slide-wrapper">
        <div
          v-for="(image, index) in visibleImages"
          :key="index"
          class="slide"
          :class="{ active: index === centerIndex }"
        >
          <img :src="image" alt="Gallery" />
        </div>
      </div>

      <button @click="nextSlide" class="nav-button">›</button>
    </div>

    <div class="dots">
      <span
        v-for="(img, idx) in images"
        :key="idx"
        :class="{ activeDot: idx === currentIndex }"
        class="dot"
        @click="goToSlide(idx)"
      ></span>
    </div>
  </section>
</template>

<script setup>
import { ref, computed, onMounted, onBeforeUnmount } from 'vue';

const images = [
  '/images/gallery-1.jpg',
  '/images/gallery-2.jpg',
  '/images/gallery-3.jpg',
  '/images/gallery-4.jpg',
  '/images/gallery-5.jpg',
  '/images/gallery-6.jpg',
  '/images/gallery-7.jpg',
  '/images/gallery-8.jpg',
];

const currentIndex = ref(0);
const visibleCount = 3;

const prevSlide = () => {
  currentIndex.value =
    (currentIndex.value - 1 + images.length) % images.length;
};

const nextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % images.length;
};

const goToSlide = (index) => {
  currentIndex.value = index;
};

const visibleImages = computed(() => {
  const visible = [];
  for (let i = 0; i < visibleCount; i++) {
    visible.push(images[(currentIndex.value + i) % images.length]);
  }
  return visible;
});

const centerIndex = Math.floor(visibleCount / 2);

// Auto-play
let autoPlayInterval;

onMounted(() => {
  autoPlayInterval = setInterval(() => {
    nextSlide();
  }, 3000); // every 3 seconds
});

onBeforeUnmount(() => {
  clearInterval(autoPlayInterval);
});
</script>

<style scoped>
.gallery-section {
  background-color: #f9f9f9;
  padding: 40px 0;
}

.slideshow {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 30px auto;
}

.slide-wrapper {
  display: flex;
  gap: 20px;
}

.slide {
  border: 5px solid transparent;
  transition: all 0.3s ease;
  background: #fff;
}

.slide.active {
  border-color: red;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
}

.slide img {
  width: 300px;
  height: 200px;
  object-fit: cover;
  border-radius: 8px;
}

.nav-button {
  font-size: 2rem;
  background: none;
  border: none;
  cursor: pointer;
  padding: 10px;
  color: #333;
}

.dots {
  text-align: center;
  margin-top: 20px;
}

.dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  background: #ccc;
  border-radius: 50%;
  margin: 0 4px;
  cursor: pointer;
  transition: background 0.3s;
}

.dot.activeDot {
  background: red;
}
</style>
