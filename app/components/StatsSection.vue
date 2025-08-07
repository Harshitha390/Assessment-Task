<template>
  <section class="stats-section">
    <div class="stats-container">
      <div class="stat-item">
        <h2>232</h2>
        <p>Clients</p>
      </div>
      <div class="stat-item">
        <h2>521</h2>
        <p>Projects</p>
      </div>
      <div class="stat-item">
        <h2>1453</h2>
        <p>Hours Of Support</p>
      </div>
      <div class="stat-item">
        <h2>32</h2>
        <p>Workers</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.stats-section {
  position: relative;
  background-image: url('/images/stats-bg.jpg');
  background-size: cover;
  background-position: center;
  padding: 120px 0;
  margin-top: -30px;
  margin-bottom: 40px;
  color: white;
  z-index: 1;
  overflow: hidden;
}

.stats-section::before {
  content: "";
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* full image overlay */
  z-index: -1;
}

/* Content inside */
.stats-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  text-align: center;
  position: relative; /* ensures it's above the ::before */
  z-index: 2;
}

.stat-item {
  flex: 1 1 200px;
  margin: 20px;
}

.stat-item h2 {
  font-size: 48px;
  margin: 0;
  font-weight: 700;
}

.stat-item p {
  margin: 0;
  font-size: 16px;
  font-weight: 700;
  color: color-mix(in srgb, white, transparent 40%);
}
</style>
