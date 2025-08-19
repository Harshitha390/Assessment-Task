<template>
  <section class="stats-section fade-in">
    <div class="stats-container fade-up" data-delay="100">
      <div class="stat-item">
        <h2 data-target="232">0</h2>
        <p>Clients</p>
      </div>
      <div class="stat-item">
        <h2 data-target="521">0</h2>
        <p>Projects</p>
      </div>
      <div class="stat-item">
        <h2 data-target="1453">0</h2>
        <p>Hours Of Support</p>
      </div>
      <div class="stat-item">
        <h2 data-target="32">0</h2>
        <p>Workers</p>
      </div>
    </div>
  </section>
</template>
<script setup>
import { onMounted } from 'vue';

onMounted(() => {
  const elements = document.querySelectorAll('.fade-up, .fade-in');
  let countersStarted = false; // ✅ flag to run only once

  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        const delay = entry.target.dataset.delay || 0;
        setTimeout(() => {
          entry.target.classList.add('show');

          // ✅ Only start counters once
          if (!countersStarted && entry.target.classList.contains('stats-container')) {
            countersStarted = true;
            startCounters(entry.target.querySelectorAll('h2[data-target]'));
          }
        }, delay);
      }
    });
  }, { threshold: 0.2 });

  elements.forEach(el => observer.observe(el));

  function startCounters(counters) {
    counters.forEach(counter => {
      const target = +counter.dataset.target;
      const duration = 1500; // ms
      const stepTime = Math.max(Math.floor(duration / target), 20);
      let current = 0;

      const timer = setInterval(() => {
        current += Math.ceil(target / (duration / stepTime));
        if (current >= target) {
          current = target;
          clearInterval(timer);
        }
        counter.textContent = current.toLocaleString();
      }, stepTime);
    });
  }
});
</script>

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
  background-color: rgba(0, 0, 0, 0.5);
  z-index: -1;
}

.stats-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  text-align: center;
  position: relative;
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

/* Fade In */
.fade-in {
  opacity: 0;
  transition: opacity 1.2s ease;
}
.fade-in.show {
  opacity: 1;
}

/* Fade Up */
.fade-up {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}
.fade-up.show {
  opacity: 1;
  transform: translateY(0);
}
</style>
