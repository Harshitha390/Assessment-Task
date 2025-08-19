<template>
  <section class="e-sec">
    <div class="party-slider" id="EventsSection">
      <swiper
        :modules="[Pagination, Autoplay]"
        :slides-per-view="3"
        :space-between="0.2"
        :pagination="{ clickable: true }"
        :autoplay="{ delay: 5000 }"
        :loop="true"
        :breakpoints="{
          0: {
            slidesPerView: 1,
          },
          768: {
            slidesPerView: 2,
          },
          1024: {
            slidesPerView: 3,
          }
        }"
      >
        <swiper-slide
          v-for="(slide, index) in slides"
          :key="index"
          class="slide"
          :style="{ backgroundImage: `url(${slide.image})` }"
        >
          <div class="content">
            <h2>{{ slide.title }}</h2>
            <h3>${{ slide.price }}</h3>
            <p>{{ slide.description }}</p>
          </div>
        </swiper-slide>

        <div class="swiper-pagination"></div>
      </swiper>
    </div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Pagination, Autoplay } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/pagination'

const slides = [
  {
    image: '/images/events-1.jpg',
    title: 'CUSTOM PARTIES',
    price: 99,
    description: 'Quo corporis voluptas ea ad. Consectetur inventore sapiente ipsum voluptates eos omnis facere.'
  },
  {
    image: '/images/events-2.jpg',
    title: 'PRIVATE PARTIES',
    price: 289,
    description: 'In delectus sint qui et enim. Et ab repudiandae inventore quaerat doloribus.'
  },
  {
    image: '/images/events-3.jpg',
    title: 'BIRTHDAY PARTIES',
    price: 499,
    description: 'Laborum aperiam atque omnis minus omnis est qui assumenda quos.'
  },
  {
    image: '/images/events-4.jpg',
    title: 'WEDDING PARTIES',
    price: 399,
    description: 'Eius distinctio minima error fugiat illo aliquid. Eveniet quas dolorum!'
  }
]
</script>

<style scoped>
.e-sec {
  color: #212529;
  padding: 60px 0;
}

.party-slider {
  width: 100%;
  position: relative;
}

.slide {
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: flex-end;
  padding: 40px;
  height: 610px;
  color: white;
  position: relative;
}

.slide::before {
  content: "";
  position: absolute;
  inset: 0;
  background-color: rgba(0, 0, 0, 0.5);

}

.content {
  position: relative;
  z-index: 2;
  max-width: 400px;
  margin-bottom: 40px;
}

.content h2 {
  font-family: 'Amatic SC', sans-serif;
  font-size: 24px;
  font-weight: 700;
  margin-bottom: 5px;
}

.content h3 {
  font-size: 32px;
  font-weight: 700;
  margin-bottom: 10px;
  border-bottom: 2px solid #ce1212;
  display: inline-block;
}

.content p {
  font-size: 16px;
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.5;
}

::v-deep .swiper-pagination-bullet {
  background-color: #ccc;
  opacity: 0.7;
 width: 12px;
 height: 12px;
}

::v-deep .swiper-pagination-bullet-active {
  background-color: #ce1212;
  opacity: 1;
  width: 12px;
  height: 12px;
}
.swiper {
  padding-bottom: 40px;
  position: relative;
}

.swiper-pagination {
  bottom: 10px;
  position: absolute;
  text-align: center;
  width: 100%;
}
/* Extra responsiveness */
@media (max-width: 1024px) {
  .slide {
    height: 500px;
    padding: 30px;
  }
  .content h2 {
    font-size: 22px;
  }
  .content h3 {
    font-size: 28px;
  }
}

@media (max-width: 768px) {
  .slide {
    height: 450px;
    padding: 25px;
  }
  .content {
    max-width: 90%;
    margin-bottom: 20px;
  }
  .content h2 {
    font-size: 20px;
  }
  .content h3 {
    font-size: 24px;
  }
  .content p {
    font-size: 15px;
  }
}

@media (max-width: 480px) {
  .slide {
    height: 400px;
    padding: 20px;
  }
  .content {
    max-width: 100%;
    margin-bottom: 15px;
  }
  .content h2 {
    font-size: 18px;
  }
  .content h3 {
    font-size: 20px;
  }
  .content p {
    font-size: 14px;
    line-height: 1.4;
  }
}
@keyframes fadeUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
.swiper-slide-active .content {
  opacity: 0; /* start hidden */
  animation-name: fadeUp;
  animation-duration: 0.6s;
  animation-timing-function: ease-out;
  animation-fill-mode: forwards;
  animation-delay: 0.2s;
}

</style>