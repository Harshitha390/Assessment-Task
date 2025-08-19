<template>
  <section class="contact-section" id="ContactSection">

    <div class="heading">
      <p class="subtitle">CONTACT</p>
       <h2 class="main-title">
      <span class="help-text">Need Help?</span>
      <span class="contact-text">Contact Us</span>
    </h2>
    </div>
    <!-- Google Map -->
    <div class="map-container">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d24176.012266364404!2d-74.0059413!3d40.7127755!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zNDDCsDQyJzQ2LjAiTiA3NMKwMDAnMjUuMCJX!5e0!3m2!1sen!2sin!4v1590161215799!5m2!1sen!2sin"
        frameborder="0"
        allowfullscreen
        loading="lazy"
      ></iframe>
    </div>

    <!-- Info Boxes -->
    <div class="info-boxes">
      <div class="info-card">
        <div class="icon"><i class="fa-solid fa-location-dot"></i></div>
        <div>
          <h3>Address</h3>
          <p>A108 Adam Street, New York, NY 535022</p>
        </div>
      </div>

      <div class="info-card">
        <div class="icon"><i class="fa-solid fa-phone"></i></div>
        <div>
          <h3>Call Us</h3>
          <p>+1 5589 55488 55</p>
        </div>
      </div>

      <div class="info-card">
        <div class="icon"><i class="fa-solid fa-envelope"></i></div>
        <div>
          <h3>Email Us</h3>
          <p>info@example.com</p>
        </div>
      </div>

      <div class="info-card">
        <div class="icon"><i class="fa-sharp fa-solid fa-clock" ></i></div>
        <div>
          <h3>Opening Hours</h3>
          <p><strong>Mon-Sat:</strong> 11AM - 23PM; <strong>Sunday:</strong> Closed</p>
        </div>
      </div>
    </div>

    <!-- Contact Form -->
    <form class="contact-form" @submit.prevent="submitForm">
      <div class="row">
        <input type="text" placeholder="Your Name" required />
        <input type="email" placeholder="Your Email" required />
      </div>
      <input type="text" placeholder="Subject" required />
      <textarea placeholder="Message" rows="6" required></textarea>
      <button type="submit">Send Message</button>
    </form>
  </section>
</template>

<script setup>
function submitForm() {
  alert("Message sent! (Form submission logic to be added)");
}
</script>

<style scoped>
.contact-section {
  text-align: center;
  padding: 60px 0px;
  background-color: white;
  max-width: 1200px;
  margin: auto;
  padding: 40px 20px;
}

.subtitle {
  text-transform: uppercase;
  font-size: 13px;
  font-weight: 400;
  color: color-mix(in srgb, #212529, transparent 50%);
  /* margin-bottom: 10px; */
  margin:0;
  padding: 0;
  letter-spacing: 1px;
}

.main-title {
  font-size: 36px;
  font-family: "Amatic SC", sans-serif;
  font-size: 48px;
  font-weight: 500px;
  margin:10px 0 0 0;
}

.help-text {
  color: #37373f;
  margin:10px 0 0 0;
}

.contact-text {
  color: #ce1212;
}

.contact-section {
  max-width: 1200px;
  margin: auto;
  padding: 40px 20px;
}

.map-container iframe {
  width: 100%;
  height: 600px;
  border: 0;
  margin-bottom: 40px;
  margin-top: 60px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.info-boxes {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  margin-bottom: 40px;
}

.info-card {
  flex: 1 1 45%;
  background: #fff;
  display: flex;
  gap: 15px;
  padding: 20px;
  box-shadow: 2px 4px 10px rgba(0, 0, 0, 0.08);
 flex-direction: row; /* keep icon and text side-by-side */
  text-align: left;    /* align text left */
  align-items: center; 
}

.info-card .icon {
  font-size: 24px;
  color: white;
  background: #ce1212;
  width: 56px;
  height: 56px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.3s ease-in-out;
}

.info-card h3 {
  margin: 0 0 5px ;
  font-size: 20px;
  font-weight: 700;
  color: color-mix(in srgb, #212529, transparent 30%);
  line-height: 1.2;
  margin: 0px 0px 5px;
  text-align: left;
}

.info-card p {
  padding: 0;
  /* margin-bottom: 0; */
  text-align: left;
  font-size: 14px;
}

.info-card div {
  display: flex;
  flex-direction: column;
}

p{
  margin-top: 0;
}

.contact-form {
  background: color-mix(in srgb, white, transparent 50%);
  padding: 30px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
  color: #212529;
  font-size: 14px;
  /* border-color: color-mix(in srgb, #212529, transparent 80%);
  
  padding: 10px 15px;
  box-shadow: none; */
}

.contact-form .row {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.contact-form input,
.contact-form textarea {
  width: 100%;
  padding: 12px;
  margin-top: 20px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.contact-form .row input {
  flex: 1 1 48%;
}

.contact-form button {
  font-size: 16px ;
  margin-top: 20px;
  padding: 10px 30px;
  background: #ce1212;
  color: white;
  border: 0;
  border-radius: 50px;
  cursor: pointer;
}

.contact-form button:hover {
  background: color-mix(in srgb, #ce1212, transparent 20%);
}

@media (max-width: 1024px) {
  .main-title {
    font-size: 40px;
  }

  .info-card {
    flex: 1 1 100%;
  }

  .map-container iframe {
    height: 400px;
  }
}

/* === Mobile (<= 768px) === */
@media (max-width: 768px) {
  .main-title {
    font-size: 36px;
  }

  .map-container iframe {
    height: 350px;
    margin-top: 40px;
  }

  .info-boxes {
    flex-direction: column;
  }

  .info-card {
    flex-direction: column;
    text-align: center;
    align-items: center;
  }

  .info-card h3,
  .info-card p {
    text-align: center;
  }

  .contact-form .row {
    flex-direction: column;
  }

  .contact-form .row input {
    flex: 1 1 100%;
  }
}

/* === Small Mobile (<= 480px) === */
@media (max-width: 480px) {
  .main-title {
    font-size: 28px;
  }

  .subtitle {
    font-size: 12px;
  }

  .map-container iframe {
    height: 300px;
  }

  .info-card {
    padding: 15px;
  }

  .info-card .icon {
    width: 48px;
    height: 48px;
    font-size: 20px;
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

.contact-section,
.subtitle,
.main-title,
.map-container,
.info-boxes,
.contact-form {
  opacity: 0;
  animation-name: fadeUp;
  animation-duration: 0.6s;
  animation-fill-mode: forwards;
  animation-timing-function: ease-out;
}

.contact-section { animation-delay: 0.1s; }
.subtitle { animation-delay: 0.2s; }
.main-title { animation-delay: 0.3s; }
.map-container { animation-delay: 0.4s; }
.info-boxes { animation-delay: 0.5s; }
.contact-form { animation-delay: 0.6s; }

</style>