<template>
  <Nav />
  <section class="hero" id="index">
    <div class="content">
      <div class="text-block">
        <h1>Enjoy Your Healthy<br />Delicious Food</h1>
        <p>We are team of talented designers making <br/>websites with Bootstrap</p>
        <div class="buttons">
          <button class="book-btn">Book a Table</button>
          <button class="video-btn">
            <i class="fa fa-play-circle" aria-hidden="true"></i>


Watch Video
          </button>
        </div>
      </div>

      <div class="image-block">
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
import Nav from '../components/Nav.vue';
import AboutSection from '~/components/AboutSection.vue';
import MenuSection from '~/components/MenuSection.vue';
import ChefSection from '~/components/ChefSection.vue';
import BookTable from '../components/BookTable.vue';
import GallerySection from '~/components/GallerySection.vue';
import WhyChooseSection from '~/components/WhyChooseSection.vue';
import Testimonials from '~/components/Testimonials.vue';
import StatsSection from '~/components/StatsSection.vue';
import EventsSection from '~/components/EventsSection.vue';
import Footer from '~/components/Footer.vue';
import ContactSection from '~/components/ContactSection.vue';
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&display=swap');
.hero {
  background-color: #F2F2F2;
  padding: 60px 0px;
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
  margin-bottom: 10px;
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
/* .icon {
  background-color: #fff;
  border: 2px solid #d32f2f;
  border-radius: 50%;
  color: #d32f2f;
  display: inline-block;
  padding: 5px 7px;
  font-size: 12px;
} */

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
</style>