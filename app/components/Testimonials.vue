<script>
export default {
  name: "TestimonialsCarousel",
  data() {
    return {
      currentIndex: 0,
      direction: 'next',
      testimonials: [
        {
          id: 1,
          quote:  "Proin iaculis purus consequat sem cure digni ssim donec porttitora entum suscipit rhoncus. Accusantium quam,ultricies eget id, aliquam eget nibh et. Maecen aliquam, risus at semper",
          name: "SAUL GOODMAN",
          role: "CEO & FOUNDER",
          image: "/images/testimonials-1.jpg",
        },
        {
          id: 2,
          quote: "Export tempor illum temen malis eram quae irure esse labore quem cillum quid cillum eram malis quorum velit fore eram velit sunt aliqua noster fugiat irure amet legam",
          name: "SARA WILSSON",
          role: "DESIGNER",
          image: "/images/testimonials-2.jpg",
        },
        {
          id: 3,
          quote: "Enim nisi quem export duis labore cillum quae magna enim sint quorum nulla quem veniam duis minim tempor labore quem eram duis noster aute amet eram fore quis sint minim",
          name: "JENA KARLIS",
          role: "STORE OWNER",
          image: "/images/testimonials-3.jpg",
        },
        {
          id: 4,
          quote: "Fugiat enim eram quae cillum dolore dolor amet nulla culpa multos export minim fugiat minim velit minim dolor enim duis veniam ipsum anim magna sunt elit fore quem dolore labore illum veniam",
          name: "JOHN LARSON",
          role: "ENTREPRENEUR",
          image: "/images/testimonials-4.jpg",
        },
      ],
      interval: null,
    };
  },
  mounted() {
    this.startSlide();
  },
  beforeDestroy() {
    clearInterval(this.interval);
  },
  methods: {
    startSlide() {
      this.interval = setInterval(() => {
        this.currentIndex = (this.currentIndex + 1) % this.testimonials.length;
      }, 7000);
    },
    goTo(index) {
      this.currentIndex = index;
    },
  },
};
</script>

<template>
  <section class="testimonial-section">
    <p class="subtitle">Testimonials</p>
    <h2 class="title">What Are They <span>Saying About Us</span></h2>

    <!-- Slide Transition -->
    <transition name="slide-fade" mode="out-in">
      <div class="carousel-wrapper" :key="testimonials[currentIndex].id">
        <div class="carousel-content">
          <div class="testimonial-card">
            <!-- Text -->
            <div class="testimonial-text">
              <p class="quote">
                <i class="fa-solid fa-quote-left"></i>
                {{ testimonials[currentIndex].quote }}
                <i class="fa-solid fa-quote-right"></i>
              </p>
              <h4 class="name">{{ testimonials[currentIndex].name }}</h4>
              <small class="role">{{ testimonials[currentIndex].role }}</small>
              <div class="stars">
                <span v-for="n in 5" :key="n">
                  <i class="fa-solid fa-star"></i>
                </span>
              </div>
            </div>

            <!-- Image -->
            <div class="testimonial-image">
              <img :src="testimonials[currentIndex].image" alt="Author Image" />
            </div>
          </div>
        </div>
      </div>
    </transition>

    <!-- Dots -->
    <div class="dots">
      <span
        v-for="(t, i) in testimonials"
        :key="i"
        :class="['dot', { active: i === currentIndex }]"
        @click="goTo(i)"
      ></span>
    </div>
  </section>
</template>

<style scoped>
/* Section layout */
.testimonial-section {
  padding: 80px 0px;
  background-color: #f2f2f2;
  text-align: center;
  color: #212529;
  scroll-margin-top: 92px;
  overflow: clip;
}

.subtitle {
  font-size: 13px;
  letter-spacing: 1px;
  font-weight: 400;
  margin: 0;
  color: rgba(33, 37, 41, 0.5);
  text-transform: uppercase;
}

.title {
  font-size: 48px;
  font-family: "Amatic SC", sans-serif;
  color: #37373f;
  margin: 10px 0 40px 0;
  font-weight: 500;
}

.title span {
  color: #ce1212;
}

/* Slide transition animation */
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.6s ease;
}

.slide-fade-enter {
  transform: translateX(100%);
  opacity: 0;
}

.slide-fade-leave-to {
  transform: translateX(-100%);
  opacity: 0;
}

/* Carousel Container */
.carousel-wrapper {
  position: relative;
  max-width: 1000px;
  margin: 0 auto;
  height: 300px;
  overflow: hidden;
}

.carousel-content {
  width: 100%;
}

/* Testimonial Card */
.testimonial-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #f2f2f2;
  padding: 30px;
}

/* Text */
.testimonial-text {
  flex: 1;
  text-align: left;
  margin: 10px 70px 0 130px;
  border-left: 3px solid #ce1212;
  padding-left: 30px;
  font-style: italic;
}

.quote {
  font-size: 16px;
  color: #212529;
  margin: 0 0 16px;
}

.quote i {
  color: rgba(206, 18, 18, 0.5);
  font-size: 20px;
}

.name {
  font: 20px "Amatic SC", sans-serif;
  font-weight: bold;
  color: #37373f;
  margin: 10px 0px 5px;
}

.role {
  font: 10px "Amatic SC", sans-serif;
  text-transform: uppercase;
  font-weight: 500;
  color: rgba(33, 37, 41, 0.4);
  margin-bottom: 10px;
}

.stars i {
  color: #ffc107;
  font-size: 16px;
  margin-top: 8px;
}

/* Image */
.testimonial-image {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  overflow: hidden;
  margin-right: 115px;
}

.testimonial-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Dots */
.dots {
  margin-top: 20px;
  display: flex;
  justify-content: center;
  gap: 10px;
}

.dot {
  height: 12px;
  width: 12px;
  background-color: #ccc;
  border-radius: 50%;
  display: inline-block;
  cursor: pointer;
}

.dot.active {
  background-color: #ce1212;
}
</style>