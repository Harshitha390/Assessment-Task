<!-- <script setup>
import { ref, computed, onMounted, onBeforeUnmount } from "vue";

const images = [
  "/images/gallery-1.jpg",
  "/images/gallery-2.jpg",
  "/images/gallery-3.jpg",
  "/images/gallery-4.jpg",
  "/images/gallery-5.jpg",
  "/images/gallery-6.jpg",
  "/images/gallery-7.jpg",
  "/images/gallery-8.jpg",
];

const visibleCount = ref(0);
const centerIndex = Math.floor(visibleCount / 2);

const currentIndex = ref(0);
const isTransitioning = ref(true);
// const newCount = ref(0)

const extendedImages = computed(() => [...images, ...images]);

const nextSlide = () => {
  isTransitioning.value = true;
  currentIndex.value++;
  console.log("currentIndex =>",currentIndex);
  // if (currentIndex.value >= images.length) {
  //   setTimeout(() => {
  //     isTransitioning.value = false;
  //     currentIndex.value = 0;
  //   }, 600);
  // }/
  if (currentIndex.value > totalSlides - visibleCount.value) {
    setTimeout(() => {
      isTransitioning.value = false;
      currentIndex.value = 0;
    }, 600);
  }
};

// const updateVisibleCount = () => {
//   const width = window.innerWidth;
//   if (width <= 425) {
//     visibleCount.value = 1;
//   } else if (width <= 768) {
//     visibleCount.value = 2;
//   } else if (width <= 1024) {
//     visibleCount.value = 3;
//   } else {
//     visibleCount.value = 5;
//   }
//   if (visibleCount.value !== newCount) {
//     visibleCount.value = newCount;
//     currentIndex.value = 0; // reset on visibleCount change
//   }
// };

const updateVisibleCount = () => {
  const width = window.innerWidth;
  let newCount;
  if (width <= 425) newCount = 1;
  else if (width <= 768) newCount = 2;
  else if (width <= 1024) newCount = 3;
  else newCount = 5;

  if (visibleCount.value !== newCount) {
    visibleCount.value = newCount;
    currentIndex.value = 0; // reset on visibleCount change to avoid misalignment
    isTransitioning.value = false;
  }
};

const goToSlide = (index) => {
  currentIndex.value = index;
};

let autoPlayInterval;
onMounted(() => {
  // autoPlayInterval = setInterval(nextSlide, 3000);
  updateVisibleCount(); // Set initially
  window.addEventListener("resize", updateVisibleCount);
  autoPlayInterval = setInterval(nextSlide, 3000);
});
onBeforeUnmount(() => {
  window.removeEventListener("resize", updateVisibleCount);
  clearInterval(autoPlayInterval);
});
</script>

<template>
  <section class="gallery-section" id="GallerySection">
    <div class="section-title">
      <h2>Gallery</h2>
      <p>
        <span>Check </span>
        <span class="description-title">Our Gallery</span>
      </p>
    </div>

    <div class="slideshow">
      <div
        class="slide-wrapper"
        :style="{
          transform: `translateX(-${currentIndex * (100 / visibleCount)}%)`,
          transition: isTransitioning ? 'transform 0.6s ease' : 'none',
        }"
      >
        <div
          v-for="(image, index) in extendedImages"
          :key="index"
          class="slide"
          :class="(index % images.length === (currentIndex + centerIndex) % images.length) ? 'active' : ''"
        >
          <div class="image-container">
            <img :src="image" alt="Gallery" />
          </div>
        </div>
      </div>
    </div>

    <div class="dots">
      <span
        v-for="(img, idx) in images"
        :key="idx"
        :class="{ activeDot: idx == currentIndex % images.length }"
        class="dot"
        @click="goToSlide(idx)"
      ></span>
    </div>
  </section>
</template>

<style scoped>
.gallery-section {
  background-color: #f2f2f2;
  padding: 100px 0;
}

.section-title {
  text-align: center;
  padding-bottom: 60px;
}

h2 {
  font-size: 13px;
  letter-spacing: 1px;
  font-weight: 400;
  margin: 0;
  color: color-mix(in srgb, #212529, transparent 50%);
  text-transform: uppercase;
}

p {
  color: #37373f;
  margin: 10px 0 0 0;
  font-size: 48px;
  font-weight: 500;
  font-family: "Amatic SC", sans-serif;
}

.description-title {
  color: #ce1212;
}

/* Center slideshow */
.slideshow {
  overflow: hidden;
  width: 100%;
  margin: 0 auto;
}

.slide-wrapper {
  display: flex;
  transition: transform 0.6s ease;
}

.slide {
  flex: 0 0 calc(100% / 5);
  box-sizing: border-box;
  padding: 0 5px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.image-container {
  width: 98%;
  height: 170px;
  background-color: transparent;
  overflow: hidden;
}

/* Middle slide with full 4-side border */
.slide.active .image-container {
  border: 5px solid #ce1212 !important;
  background-color: #fff;
  box-sizing: border-box;
}

.slide img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  padding: 6px;
}

.dots {
  text-align: center;
  margin-top: 30px;
}

.dot {
  display: inline-block;
  width: 12px;
  height: 12px;
  background: #ccc;
  border-radius: 50%;
  margin: 0 4px;
  cursor: pointer;
}

.dot.activeDot {
  background: #ce1212;
}
/* Responsive for tablets and smaller desktops */
@media (max-width: 1024px) {
  .slide {
    flex: 0 0 calc(100% / 3); /* show 3 slides */
  }
}

/* Responsive for tablets and large phones */
@media (max-width: 768px) {
  .slide {
    flex: 0 0 calc(100% / 2); /* show 2 slides */
  }
}

@media (max-width: 425px) {
  .slide {
    flex: 0 0 100%;
  }
  .image-container {
    height: 200px;
  }
}

@media (max-width: 375px) {
  .slide {
    flex: 0 0 100%;
  }
}

@media (max-width: 320px) {
  .slide {
    flex: 0 0 100%;
  }
}
</style> -->
<script setup>
import { ref, computed, onMounted, onBeforeUnmount } from "vue";

const images = [
  "/images/gallery-1.jpg",
  "/images/gallery-2.jpg",
  "/images/gallery-3.jpg",
  "/images/gallery-4.jpg",
  "/images/gallery-5.jpg",
  "/images/gallery-6.jpg",
  "/images/gallery-7.jpg",
  "/images/gallery-8.jpg",
];

const visibleCount = ref(0);
// Make centerIndex reactive by making it computed based on visibleCount.value
const centerIndex = computed(() => Math.floor(visibleCount.value / 2));

const currentIndex = ref(0);
const isTransitioning = ref(true);

const extendedImages = computed(() => [...images, ...images]);

const totalSlides = images.length;

const nextSlide = () => {
  isTransitioning.value = true;
  currentIndex.value++;
  if (currentIndex.value > totalSlides) {
    setTimeout(() => {
      isTransitioning.value = false;
      currentIndex.value = 0;
    }, 600);
  }
};

const updateVisibleCount = () => {
  const width = window.innerWidth;
  let newCount;
  if (width <= 425) newCount = 1;
  else if (width <= 768) newCount = 2;
  else if (width <= 1024) newCount = 3;
  else newCount = 5;

  if (visibleCount.value !== newCount) {
    visibleCount.value = newCount;
    currentIndex.value = 0;
    isTransitioning.value = false;
  }
};

const goToSlide = (index) => {
  currentIndex.value = index;
};

let autoPlayInterval;
onMounted(() => {
  updateVisibleCount(); 
  window.addEventListener("resize", updateVisibleCount);
  autoPlayInterval = setInterval(nextSlide, 3000);
});
onBeforeUnmount(() => {
  window.removeEventListener("resize", updateVisibleCount);
  clearInterval(autoPlayInterval);
});
</script>

<template>
  <section class="gallery-section" id="GallerySection">
    <div class="section-title">
      <h2>Gallery</h2>
      <p>
        <span>Check </span>
        <span class="description-title">Our Gallery</span>
      </p>
    </div>

    <div class="slideshow">
      <div
        class="slide-wrapper"
        :style="{
          transform: `translateX(-${currentIndex * (100 / visibleCount)}%)`,
          transition: isTransitioning ? 'transform 0.6s ease' : 'none',
        }"
      >
        <div
          v-for="(image, index) in extendedImages"
          :key="index"
          class="slide"
          :class="(index % images.length === (currentIndex + centerIndex) % images.length) ? 'active' : ''"
        >
          <div class="image-container ">
            <img :src="image" alt="Gallery" />
          </div>
        </div>
      </div>
    </div>

    <div class="dots">
      <span
        v-for="(img, idx) in images"
        :key="idx"
        :class="{ activeDot: idx === currentIndex % images.length }"
        class="dot"
        @click="goToSlide(idx)"
      ></span>
    </div>
  </section>
</template>

<style scoped>
.gallery-section {
  background-color: #f2f2f2;
  padding: 100px 0;
}

.section-title {
  text-align: center;
  padding-bottom: 60px;
}

h2 {
  font-size: 13px;
  letter-spacing: 1px;
  font-weight: 400;
  margin: 0;
  color: color-mix(in srgb, #212529, transparent 50%);
  text-transform: uppercase;
}

p {
  color: #37373f;
  margin: 10px 0 0 0;
  font-size: 48px;
  font-weight: 500;
  font-family: "Amatic SC", sans-serif;
}

.description-title {
  color: #ce1212;
}

/* Center slideshow */
.slideshow {
  overflow: hidden;
  width: 80%;
  margin: 0 auto;
}

.slide-wrapper {
  display: flex;
  transition: transform 0.6s ease;
}

.slide {
  flex: 0 0 calc(100% / 5);
  box-sizing: border-box;
  padding: 0 5px;
  display: flex;
  align-items: center;
  justify-content: center;
}


.image-container {
  width: 100%;
  height: 170px;
  background-color: transparent;
  overflow: hidden;
}

/* Middle slide with full 4-side border */
/* .slide.active .image-container {
  border: 5px solid #ce1212 !important;
  background-color: #fff;
  box-sizing: border-box;
} */

.slide.active .image-container {
  border: 7px solid #ce1212; 
  background-color: #fff;
  padding: 2px;
  box-sizing: border-box;
  box-shadow: 0 0 15p white(206, 18, 18, 0.7);
  
}

.slide img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  padding: 2px;
}

.dots {
  text-align: center;
  margin-top: 30px;
}

.dot {
  display: inline-block;
  width: 12px;
  height: 12px;
  background: #ccc;
  border-radius: 50%;
  margin: 0 4px;
  cursor: pointer;
}

.dot.activeDot {
  background: #ce1212;
}

/* Responsive for tablets and smaller desktops */
@media (max-width: 1024px) {
  .slide {
    flex: 0 0 calc(100% / 3);
  }
}

/* Responsive for tablets and large phones */
@media (max-width: 768px) {
  .slide {
    flex: 0 0 calc(100% / 2);
  }
}

@media (max-width: 425px) {
  .slide {
    flex: 0 0 100%;
  }
  .image-container {
    height: 200px;
  }
}

@media (max-width: 375px) {
  .slide {
    flex: 0 0 100%;
  }
}

@media (max-width: 320px) {
  .slide {
    flex: 0 0 100%;
  }
}
</style>

