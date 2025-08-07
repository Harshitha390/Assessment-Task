<template>
  <section class="menu-section" id="menu">
    <!-- Menu Subtitle -->
    <transition name="fade">
      <p class="menu-subtitle" key="subtitle">Our Menu</p>
    </transition>

    <!-- Menu Title -->
    <transition name="fade">
      <h2 class="menu-title" key="title">
        Check Our <span>Yummy Menu</span>
      </h2>
    </transition>

    <!-- Tabs -->
    <transition name="fade">
      <div class="menu-tabs" key="tabs">
        <button
          v-for="tab in tabs"
          :key="tab"
          @click="activeTab = tab"
          :class="['tab-button', { active: activeTab === tab }]"
        >
          {{ tab }}
        </button>
      </div>
    </transition>

    <!-- Main Heading -->
    <transition name="slide-fade">
      <h3 class="menu-main-heading" :key="`main-${activeTab}`">MENU</h3>
    </transition>

    <!-- Tab Heading -->
    <transition name="slide-fade">
      <h3 class="tab-heading" :key="`heading-${activeTab}`">
        {{ activeTab }}
      </h3>
    </transition>

    <!-- Menu Items -->
    <transition-group name="menu-fade" tag="div" class="menu-grid">
      <div
        v-for="item in filteredItems"
        :key="item.title + activeTab"
        class="menu-card"
      >
        <img :src="item.image" alt="Menu item" class="menu-img" />
        <h4 class="menu-name">{{ item.title }}</h4>
        <p class="menu-desc">Lorem, deren, trataro, filede, nerada</p>
        <span class="menu-price">${{ item.price }}</span>
      </div>
    </transition-group>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const tabs = ['Starters', 'Breakfast', 'Lunch', 'Dinner']
const activeTab = ref('Starters')

const menuItems = ref([
  {
    title: 'Magnam Tiste',
    category: ['Starters', 'Breakfast', 'Lunch', 'Dinner'],
    price: 5.95,
    image: '/images/img1.png'
  },
  {
    title: 'Aut Luia',
    category: ['Starters', 'Breakfast', 'Lunch', 'Dinner'],
    price: 14.95,
    image: '/images/menu-item-2.png'
  },
  {
    title: 'Est Eligendi',
    category: ['Starters', 'Breakfast', 'Lunch', 'Dinner'],
    price: 8.95,
    image: '/images/menu-item-3.png'
  },
  {
    title: 'Salad Mix',
    category: ['Starters', 'Breakfast', 'Lunch', 'Dinner'],
    price: 7.95,
    image: '/images/menu-item-4.png'
  },
  {
    title: 'Steak & Veggies',
    category: ['Starters', 'Breakfast', 'Lunch', 'Dinner'],
    price: 16.95,
    image: '/images/menu-item-5.png'
  },
  {
    title: 'Mushroom Bowl',
    category: ['Starters', 'Breakfast', 'Lunch', 'Dinner'],
    price: 9.95,
    image: '/images/menu-item-6.png'
  }
])

const filteredItems = computed(() =>
  menuItems.value.filter(item => item.category.includes(activeTab.value))
)
</script>

<style scoped>
.menu-section {
  padding: 60px 0px;
  text-align: center;
}

/* Headings and Titles */
.menu-subtitle {
  text-transform: uppercase;
  font-size: 13px;
  letter-spacing: 1px;
  font-weight: 400;
  margin-top: -20px;
  color: color-mix(in srgb, #212529, transparent 50%);
  display: inline-block;
  font-family: "Roboto", sans-serif;
}

.menu-title {
  color: #37373f;
  margin: 10px 0 0 0;
  font-size: 48px;
  font-weight: 500;
  font-family: "Amatic SC", sans-serif;
}
.menu-title span {
  color: #ce1212;
}

.menu-main-heading {
  font-size: 14px;
  color: 
 color-mix(in srgb, #212529, transparent 20%);
  text-transform: uppercase;
  font-family: "Roboto", sans-serif;
  margin-top: 30px;
  margin-bottom: 0;
  letter-spacing: 1px;
}

.tab-heading {
  margin-bottom: 40px;
  font-size: 48px;
  font-weight: 700;
  color: #ce1212;
  font-family: "Amatic SC", sans-serif;
}

/* Tabs */
.menu-tabs {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 20px;
  font-family: "Roboto", sans-serif;
  margin-top: 40px;
  padding: 10px 5px;
  cursor: pointer;
}
.tab-button {
  background: none;
  border: none;
  font-weight: 400;
  font-size: 18px;
  padding-bottom: 5px;
  /* border-bottom: 2px solid transparent; */
  border-bottom: 2px solid #ddd;
  cursor: pointer;
  color: #444;
  position:relative;
}
.tab-button:hover {
  border-color: #b30000;
}
.tab-button.active{
  border-color: #b30000;
}

/* Menu Cards Grid */
.menu-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 40px;
  max-width: 1100px;
  margin: 0 auto;
}
.menu-card {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.menu-img {
  width: 250px;
  height: 250px;
  object-fit: cover;
  margin-bottom: 15px;
  margin-top: 20px;
}
.menu-name {
  font-size: 24px;
  font-weight: 400;
  margin: 0px 0px 5px;
  color: #37373f;
  font-family: "Roboto", sans-serif;
}
.menu-desc {
  font: 16px "Inter", sans-serif;
  color: color-mix(in srgb, #212529, transparent 50%);
  margin-bottom: 5px;
}
.menu-price {
  color: #ce1212;
  font-size: 24px;
  font-weight: 700;
}

/* Fade Animation */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Slide-Fade Animation for Headings */
.slide-fade-enter-active {
  transition: all 0.5s ease;
}
.slide-fade-enter-from {
  opacity: 0;
  transform: translateY(20px);
}
.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

/* Menu Items Stagger Animation */
.menu-fade-enter-active {
  transition: all 0.5s ease;
}
.menu-fade-enter-from {
  opacity: 0;
  transform: scale(0.95);
}
.menu-fade-leave-to {
  opacity: 0;
  transform: scale(0.95);
}
</style>
