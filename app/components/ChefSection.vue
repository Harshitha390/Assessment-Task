<template>
  <section class="chef-section" id="ChefSection">
    <div class="title">
      <small>CHEFS</small>
      <h2>Our <span>Proffesional Chefs</span> </h2><br>
    </div>

    <div class="chef-grid">
      <div v-for="chef in chefs" :key="chef.name" class="chef-card">
        <img :src="chef.image" :alt="chef.name" />
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
      "Velit aut quia fugit et et. Dolorum ea voluptate vel tempore tenetur ipsa quae aut. Ipsum exercitationem iure minima enim corporis et voluptate.",
  },
  {
    name: "Sarah Jhonson",
    role: "Patissier",
    image: "/images/chefs-2.jpg",
    description:
      "Quo esse repellendus quia id. Est eum et accusantium pariatur fugit nihil minima suscipit corporis. Voluptate sed quas reiciendis animi neque sapiente.",
  },
  {
    name: "William Anderson",
    role: "Cook",
    image: "images/chefs-3.jpg",
    description:
      "Vero omnis enim consequatur. Voluptas consectetur unde qui molestiae deserunt. Voluptates enim aut architecto porro aspernatur molestiae modi.",
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
  gap: 2rem;
  justify-content: center;
  margin-top: 2rem;
}
.chef-card {
  width: 300px;
  background: #fff;
  overflow: hidden;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.1);
}
.chef-card img {
  width: 100%;
  height: 300px;
  object-fit: cover;
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
  color: color(srgb 0.129412 0.145098 0.160784 0.5);
  margin-bottom: 0.5rem;
}
.chef-info .desc {
 font: 14px "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  color: color(srgb 0.129412 0.145098 0.160784 0.7);
  padding: 15px 0px 0px;
  margin: 0px 0px 16px;
}

</style>
