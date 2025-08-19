<template>
  <NavBar />
  <section class="hero" id="index">
    <div class="content">
      <div class="text-block fade-up-target">
        <h1>Enjoy Your Healthy<br />Delicious Food</h1>
        <p>
          We are team of talented designers making <br />
          websites with Bootstrap
        </p>
        <div class="buttons fade-up-target">
          <button class="book-btn"><a href="#BookTable">Book a Table</a></button>
          <button class="video-btn">
            <i class="fa fa-play-circle" aria-hidden="true"></i>
            Watch Video
          </button>
        </div>
      </div>
      <div class="image-block zoom-target">
        <img src="/images/img1.png" alt="Healthy Food" />
      </div>
    </div>
  </section>

  <AboutSection />
  <WhyChooseSection />
  <StatsSection />
  <MenuSection />
  <Testimonials />
  <EventsSection />
  <ChefSection />
  <BookTable />
  <GallerySection />
  <ContactSection />
  <Footer />
</template>

<script>
import { onMounted } from "vue";
import AboutSection from "~/components/AboutSection.vue";
import MenuSection from "~/components/MenuSection.vue";
import ChefSection from "~/components/ChefSection.vue";
import BookTable from "../components/BookTable.vue";
import GallerySection from "~/components/GallerySection.vue";
import WhyChooseSection from "~/components/WhyChooseSection.vue";
import Testimonials from "~/components/Testimonials.vue";
import StatsSection from "~/components/StatsSection.vue";
import EventsSection from "~/components/EventsSection.vue";
import Footer from "~/components/Footer.vue";
import ContactSection from "~/components/ContactSection.vue";
import NavBar from "~/components/NavBar.vue";

export default {
  components: {
    NavBar,
    AboutSection,
    MenuSection,
    ChefSection,
    BookTable,
    GallerySection,
    WhyChooseSection,
    Testimonials,
    StatsSection,
    EventsSection,
    Footer,
    ContactSection,
  },
  setup() {
onMounted(() => {
  const targets = document.querySelectorAll(".zoom-target");
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("zoom-out");
          observer.unobserve(entry.target);
        }
      });
    },
    { threshold: 0.2 }
  );
  targets.forEach((target) => observer.observe(target));

  const textEls = document.querySelectorAll(".text-block h1, .text-block p, .text-block .buttons");
  const textObserver = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          textEls.forEach((el, i) => {
            setTimeout(() => {
              el.classList.add("fade-up");
            }, i * 200);
          });
          textObserver.disconnect();
        }
      });
    },
    { threshold: 0.2 }
  );
  if (textEls.length) {
    textObserver.observe(textEls[0]);
  }
});

  },
};
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&display=swap');
html, body {
  overflow-x: hidden;
}

.hero {
  background-color: #F2F2F2;
  padding: 60px 0px;
  margin: 0;
  min-height: 60vh;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  position: relative;
}

.content {
  display: flex;
  flex-wrap: wrap;
  max-width: 1200px;
  width: 100%;
  align-items: center;
  justify-content: space-between;
  gap: 40px;
}

.text-block {
  flex: 1;
  min-width: 300px;
  padding-top: 30px;
  padding-left: 30px;
}

.text-block h1 {
  font: 64px "Amatic SC", sans-serif;
  color: #37373F;
  line-height: 1.4;
  margin-bottom: 20px;
  margin: 0;
  font-size: 64px;
  font-weight: 700;
}

.text-block p {
  color: color-mix(in srgb, #212529, transparent 30%);
  font:20px Roboto,system-ui,-apple-system;
  margin:5px 0px 30px;
  font-size: 20px;
  font-weight: 400;
  
}

i{
  color: #ce1212
}
.buttons {
  display: flex;
  align-items: center;
  gap: 16px;
  flex-wrap: nowrap;
}

.book-btn {
  background-color: #C11212;
  color: white;
  padding: 10px 28px 12px 28px;
  border: none;
  border-radius: 50px;
  font-weight: 400;
  font-size:15px ;
  box-shadow: 0 4px 10px rgba(211, 47, 47, 0.4);
  cursor: pointer;
  transition: 0.5s;
  letter-spacing:1px;
  display:inline-block;
  margin-bottom: 0;
  box-sizing: 0 8px 28px rgba(0,0,0,0.1);
}

.book-btn:hover {
  background-color: rgba(211, 47, 47, 0.9) ; 
}

.video-btn {
  background: transparent;
  border: none;
  color: #212529;
  font: 16px Roboto, system-ui -apple-system;
  font-weight: 500;
  margin-left: 10px;
  padding-bottom: 12px;
  display: flex;
  align-items: center;
  gap: 6px;
  cursor: pointer;
  transition: 0.5s;
}

i{
    color: #c11212;
    font-size: 32px;
    line-height: 0;
    margin-right: 3px;
    transition: 0.3s;
}

.vedio-btn:hover{ 
  color: #C11212;
}

.image-block {
  flex: 1;
  min-width: 500px;
  text-align: center;
  padding-top: 70px;
  padding-left: 100px;
}
.image-block img {
  width: 450px;
  height: 450px;
  border-radius: 100%;
  object-fit: cover;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  animation: floatUpDown 4s ease-in-out infinite; 
}
@keyframes floatUpDown {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
  100% {
    transform: translateY(0px);
  }
}
.image-block {
  flex: 1;
  min-width: 500px;
  text-align: center;
  padding-top: 70px;
  padding-left: 100px;
  opacity: 0; 
  transform: scale(1.2);
  transition: opacity 1s ease, transform 1s ease;
}

.image-block img {
  width: 450px;
  height: 450px;
  border-radius: 100%;
  object-fit: cover;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  animation: floatUpDown 4s ease-in-out infinite;
}

@keyframes floatUpDown {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
  100% {
    transform: translateY(0px);
  }
}

.zoom-out {
  opacity: 1;
  transform: scale(1);
}
.text-block h1,
.text-block p,
.text-block .buttons {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}

.text-block h1.fade-up,
.text-block p.fade-up,
.text-block .buttons.fade-up {
  opacity: 1;
  transform: translateY(0);
}

@media (max-width: 1024px) {
  .content {
    
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 30px;
    padding: 0 20px;
  }

  .text-block {
    padding-left: 0;
    padding-top: 0;
    text-align: left;
  }

  .image-block {
    order: -1;
    padding-left: 12px;
    padding-right: 12px;
    /* padding-top: 80px; */
    min-width: auto;
  }

  .image-block img {
    margin: 24px;
    /* height: 550px;
    width: 550px; */
    width: 100%;
    max-width: 550px;
    height: auto;
  }
  .buttons{
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: flex-start; 
    gap: 16px;
  }
}
@media (max-width: 768px) {
  .hero {
  
    padding: 40px 0;
    min-height: auto;
  }

  .text-block h1 {
    margin-top: -20px;
    font-size: 48px;
  }

  .text-block p {
    font-size: 18px;
    margin-bottom: 20px;
  }

  .book-btn {
    font-size: 14px;
    padding: 8px 10px;
  }

  .video-btn {
    font-size: 14px;
  }

  .image-block img {
    /* width: 300px;
    height: 300px; */
    width: 100%;
    max-width: 600px; /* Increase from 300px to something bigger */
    height: auto;
  }
}

@media (max-width: 480px) {
  .text-block h1 {
    font-size: 36px;
    line-height: 1.2;
  }

  .text-block p {
    font-size: 16px;
  }

  .image-block img {
    /* width: 250px;
    height: 250px; */
    width: 100%;
    max-width: 450px; /* Larger than your current 250px */
    height: auto;
  }

  .buttons {
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    gap: 12px;
  }

  .book-btn,
  .video-btn {
    flex: 1 1 auto;
    justify-content: center;
  }
}
</style>