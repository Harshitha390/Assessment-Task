[media pointer="file-service://file-AwpFmrHt74QFPAaTL3Jcbk"]
<template>
  <section class="chef-section" id="ChefSection">
    <div class="title">
      <small>CHEFS</small>
      <h2>Our <span>Professional Chefs</span></h2>
      <br />
    </div>

    <div class="chef-grid">
      <div v-for="chef in chefs" :key="chef.name" class="chef-card" >
        
        <div class="wave-image">
          <img :src="chef.image" :alt="chef.name" />

          <!-- Social Media Icons -->
          <div class="social-links">
            <a :href="chef.social.facebook" target="_blank"><i class="fa-brands fa-facebook"></i></a>
            <a :href="chef.social.twitter" target="_blank"><i class="fa-brands fa-x-twitter"></i></a>
            <a :href="chef.social.instagram" target="_blank"><i class="fab fa-instagram"></i></a>
            <a :href="chef.social.linkedin" target="_blank"><i class="fa-brands fa-linkedin"></i></a>
          </div>

          <!-- Wave Shape -->
          <svg viewBox="0 0 500 150" preserveAspectRatio="none">
            <path
              d="M0.00,49.98 C150.00,150.00 349.69,-50.00 500.00,49.98 L500.00,150.00 L0.00,150.00 Z"
              style="stroke: none; fill: white;"
            ></path>
          </svg>
        </div>

        <div class="chef-info">
          <h3>{{ chef.name }}</h3>
          <p class="role">{{ chef.role }}</p>
          <p class="desc">{{ chef.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const chefs = [
  {
    name: "Walter White",
    role: "Master Chef",
    image: "/images/chefs-1.jpg",
    description:
      "Velit aut quia fugit et et. Dolorum ea voluptate vel tempore tenetur ipsa quae aut.",
    social: {
      facebook: "#",
      twitter: "#",
      instagram: "#",
      linkedin: "#",
    },
  },
  {
    name: "Sarah Jhonson",
    role: "Patissier",
    image: "/images/chefs-2.jpg",
    description:
      "Quo esse repellendus quia id. Est eum et accusantium pariatur fugit nihil minima suscipit.",
    social: {
      facebook: "#",
      twitter: "#",
      instagram: "#",
      linkedin: "#",
    },
  },
  {
    name: "William Anderson",
    role: "Cook",
    image: "/images/chefs-3.jpg",
    description:
      "Vero omnis enim consequatur. Voluptas consectetur unde qui molestiae deserunt.",
    social: {
      facebook: "#",
      twitter: "#",
      instagram: "#",
      linkedin: "#",
    },
  },
];
</script>


<style scoped>
.chef-section {
  text-align: center;
      color: #212529;
    padding: 60px 0;
    overflow: clip;
}
.title small {
     font-size: 13px;
    letter-spacing: 1px;
    font-weight: 400;
    padding: 0;
    margin: 0;
    color: color-mix(in srgb, #212529, transparent 50%);
    display: inline-block;
    text-transform: uppercase;
    font-family: "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
}
.title h2 {
  
  margin-top: 0.5rem;
  color: #37373f;
    margin: 10px 0 0 0;
    font-size: 48px;
    font-weight: 500;
    font-family: "Amatic SC", sans-serif;
}
.title span {
  color: #ce1212;
}
.chef-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
  margin-top: 2rem;
}
.chef-card {
  width: 350px;
  background: #fff;
  overflow: hidden;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.1);
  transition: transform 0.4s ease, box-shadow 0.4s ease;
  border-radius: 5px;
  position: relative;
}

.chef-card:hover {
  transform: scale(1.05); 
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.chef-card img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 5px;
}

.chef-info {
  padding: 1rem;
}

.chef-info h3 {
  color: #37373f;
  font: 20px "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-weight: bold;
  margin: 0px 0px 5px;
}
.chef-info .role {
   font: 14px "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
   margin-bottom: 0.5rem;
    display: block;
    font-size: 14px;
    font-weight: 400;
    color: color-mix(in srgb, #212529, transparent 50%);
}

.chef-info .desc {
  font: 14px "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  padding: 15px 0px 0px;
  margin: 0px 0px 16px;

  font-style: italic;
  /* padding-top: 15px; */
  line-height: 26px;
  color: color-mix(in srgb, #212529, transparent 30%);
}

.wave-image {
  position: relative;
  width: 100%;
  height: 300px;
  overflow: hidden;
}

.wave-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.5s ease;
}

.chef-card:hover .wave-image img {
  transform: scale(1.1);
}

.wave-image svg {
  position: absolute;
  bottom: -1px; 
  left: 0;
  width: 100%;
  height: 50px;
} 

/* Social Media Overlay */
.social-links {
  position: absolute;
  top: 10px;
  right: -50px;
  display: flex;
  flex-direction: column;
  gap: 6px;
  transition: right 0.3s ease;
  
}

.social-links a {
  background: white;
  color: #37373f;
  padding: 8px;
  border-radius: 50%;
  text-align: center;
  font-size: 14px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  transition: background 0.3s ease, color 0.3s ease;
  
}

.social-links a:hover {
  background: #ce1212;
  color: white;
}

.chef-card:hover .social-links {
  right: 10px;
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
</style>