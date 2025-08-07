<template>
    <section class="why-choose">
  <!-- Left red content box -->
  <div class="left-box">
    <h2>Why Choose<br />Yummy</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
      incididunt ut labore et dolore magna aliqua. Duis aute irure dolor in reprehenderit.
      Asperiores dolores sed et. Tenetur quia eos. Autem tempore quibusdam vel necessitatibus
      optio ad corporis.
    </p>
    <button class="learn-btn">Learn More <i class="fa-solid fa-chevron-right"></i></button>
  </div>

  <!-- Feature cards -->
  <div class="feature-card">
    <div class="icon-circle">
      <i class="fas fa-clipboard-list"></i>
    </div>
    <h4>Corporis voluptates officia eiusmod</h4>
    <p>Consequuntur sunt aut quasi enim aliquam quae harum pariatur laboris nisi ut aliquip</p>
  </div>

  <div class="feature-card">
    <div class="icon-circle">
      <i class="fa-regular fa-gem"></i>
    </div>
    <h4>Ullamco laboris ladore lore pan</h4>
    <p>Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt</p>
  </div>

  <div class="feature-card">
    <div class="icon-circle">
      <i class="fa-solid fa-inbox"></i>
    </div>
    <h4>Labore consequatur incidid dolore</h4>
    <p>Aut suscipit aut cum nemo deleniti aut omnis. Doloribus ut maiores omnis facere</p>
  </div>
</section>

</template>

<style>
.why-choose {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
  padding: 2rem;
  background-color: #f3f4f6;
  box-sizing: border-box;
}

/* Left red content box */
.left-box {
  background-color: #c11212; 
  color: white;
  padding: 30px;
  max-width: 350px;
  width: 100%;
  box-sizing: border-box;
  margin-top: 40px;
  margin-left: -6px;
  margin-bottom: 60px;
  padding-right: 20px;
}

.left-box h2 {
  font-family: "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-weight: 700;
  font-size: 34px;
  margin-bottom: 30px;
}

.left-box p {
  margin-bottom: 1.5rem;
}

.learn-btn {
 background-color: color-mix(in srgb, white, transparent 85%);
  color: white;
  font: 16px Roboto,system-ui;
  border-radius: 9999px;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s;
      padding: 8px 40px 10px

}
.left-box .learn-btn{
  align-items: center; 
}

.learn-btn:hover {
  color: #ce1212;
  background-color: white;
}

/* Feature cards */
.feature-card {
  background-color: white;
  text-align: center;
  padding: 1.5rem;
  margin-left: 8px;
  margin-top: 40px;
  margin-bottom: 60px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 240px;
  box-sizing: border-box;
    border: 1px solid color-mix(in srgb, #212529, transparent 90%);
    
}

.icon-circle {
 background-color: color-mix(in srgb, #ce1212, transparent 95%);
 height: 72px;
 width: 72px;
 border-radius: 50%;
 display: inline-flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto 1rem;
  padding: 1rem;
  color: #CE1212; 
  font-size: 32px;
  margin-top: 40px;
}

/* .icon-circle i {
  color: #CE1212; 
  font-size: 32px; /* text-2xl */


 .why-choose .feature-card:hover i {
  background-color :#CE1212;
  color: white;
} 

.feature-card h4{
  font-weight: 500;
  padding: 10px 18px;
  margin-top: 10px;
  line-height: normal;
  font-size: 20px;
  color: #37373f;
    font-family: "Roboto", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
} 

.feature-card p {
    font-size: 15px;
    padding: 8px 15px;
    margin-top: 20px;
    color: color-mix(in srgb, #212529, transparent 30%);
}
</style>