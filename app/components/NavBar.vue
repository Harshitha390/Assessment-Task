<template>
  <header class="navbar">
    <div class="navbar-container">
      
      <div class="logo">Yummy<span class="dot">.</span></div>

      <nav class="nav-links" :class="{ 'show-mobile-menu': mobileMenuOpen }">
        <ul>
          <li><a href="#index" :class="{ active: activeLink === 'index' }" @click="setActive('index')">Home</a></li>
          <li><a href="#AboutSection" :class="{ active: activeLink === 'about' }" @click="setActive('about')">About</a></li>
          <li><a href="#menu" :class="{ active: activeLink === 'menu' }" @click="setActive('menu')">Menu</a></li>
          <li><a href="#EventsSection" :class="{ active: activeLink === 'events' }" @click="setActive('events')">Events</a></li>
          <li><a href="#ChefSection" :class="{ active: activeLink === 'chefs' }" @click="setActive('chefs')">Chefs</a></li>
          <li><a href="#GallerySection" :class="{ active: activeLink === 'gallery' }" @click="setActive('gallery')">Gallery</a></li>

          <li class="dropdown" @mouseover="dropdownOpen = true" @mouseleave="dropdownOpen = false">
            <a href="#index">Dropdown <i class="fa-solid fa-chevron-down"></i></a>
            <transition name="fade">
              <ul v-show="dropdownOpen" class="dropdown-menu">
                <li><a href="#">Dropdown 1</a></li>
                <li class="deep-dropdown" @mouseover.stop="deepDropdownOpen = true" @mouseleave.stop="deepDropdownOpen = false">
                  <a href="#">Deep Dropdown <i class="fa-solid fa-chevron-down"></i></a>
                  <transition name="fade">
                    <ul v-show="deepDropdownOpen" class="deep-menu">
                      <li><a href="#">Deep Dropdown 1</a></li>
                      <li><a href="#">Deep Dropdown 2</a></li>
                      <li><a href="#">Deep Dropdown 3</a></li>
                      <li><a href="#">Deep Dropdown 4</a></li>
                      <li><a href="#">Deep Dropdown 5</a></li>
                    </ul>
                  </transition>
                </li>
                <li><a href="#">Dropdown 2</a></li>
                <li><a href="#">Dropdown 3</a></li>
                <li><a href="#">Dropdown 4</a></li>
              </ul>
            </transition>
          </li>

          <li><a href="#ContactSection" :class="{ active: activeLink === 'contact' }" @click="setActive('contact')">Contact</a></li>
        </ul>
      </nav>

      <div class="nav-actions">
        <button class="book-btn"><a href="#BookTable">Book a Table</a></button>
        <button class="hamburger" @click="mobileMenuOpen = !mobileMenuOpen">
          <i class="fa-solid" :class="mobileMenuOpen ? 'fa-xmark' : 'fa-bars'"></i>
        </button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      dropdownOpen: false,
      deepDropdownOpen: false,
      activeLink: 'index',
      mobileMenuOpen: false
    };
  },
  methods: {
    setActive(link) {
      this.activeLink = link;
      this.mobileMenuOpen = false;
    },
    onScroll() {
      const sections = [
        { id: 'index', offset: 0 },
        { id: 'AboutSection' },
        { id: 'menu' },
        { id: 'EventsSection' },
        { id: 'ChefSection' },
        { id: 'GallerySection' },
        { id: 'ContactSection' }
      ];
      const scrollPos = window.scrollY + 100;
      for (let i = sections.length - 1; i >= 0; i--) {
        const section = document.getElementById(sections[i].id);
        if (section && section.offsetTop <= scrollPos) {
          this.activeLink = sections[i].id.toLowerCase().replace('section', '');
          break;
        }
      }
    },
  },
  mounted() {
    window.addEventListener('scroll', this.onScroll);
    this.onScroll();
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.onScroll);
  }
};
</script>

<style scoped>
.navbar {
  background: #fff;
  padding: 20px 0;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  position: fixed;
  width: 100%;
  height: 85px;
  top: 0;
  z-index: 1000;
}

.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 20px;
  margin: 0px 49px;
}

.logo {
  font-size: 30px;
  font-weight: 700;
  color: #37373f;
  font-family: "Roboto" system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  margin-left: 38px;
  margin-right: 40px;
}

.dot {
  color: #CE1212;
  font-size: 25px;
}

.nav-links ul {
  display: flex;
  list-style: none;
  gap: 10px;
  margin-left: -50px;
  padding: 0;
}
.nav-links a {
  text-decoration: none;
  padding: 10px 0;
  margin-left: 20px;
  color: #7f7f90;
  font-size: 15px;
  font-weight: 500;
  font-family: "Inter", sans-serif;
  position: relative;
  transition: color 0.3s;
}

.nav-links a::before {
  content: '';
  position: absolute;
  left: 0;
  bottom: -4px;
  width: 0%;
  height: 2px;
  background-color: #ce1212;
  transition: width 0.3s ease;
}
.nav-links a:hover::before {
  width: 100%;
}
.nav-links a:hover {
  color: #37373f;
}
.nav-links a.active {
  color: #37373f;
}
.nav-links a.active::before {
  width: 100%;
}

.dropdown-menu li a::before,
.deep-menu li a::before {
  content: none;
}

.dropdown {
  position: relative;
}

.dropdown-menu {
  position: absolute;
  top: 150%;
  left: 70px;
  background: white;
  min-width: 200px;
  display: flex;
  flex-direction: column;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  padding: 8px 0;
  margin-left: 0;
  z-index: 100;
  line-height: 1px;
}
.dropdown-menu li {
  position: relative;
}
.dropdown-menu li a {
  display: block;
  padding: 15px 16px; 
  margin: 0; 
  color: #333;
  white-space: nowrap;
  transition: color 0.3s, background 0.3s;
}
.dropdown-menu li a:hover {
  background: #f8f8f8;
  color: #CE1212;
}

.deep-dropdown {
  position: relative;
}
.deep-menu {
  position: absolute;
  top: 0;
  right: 100%;
  background: white;
  display: flex;
  flex-direction: column;
  min-width: 200px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  padding: 8px 0;
  z-index: 101;
}

.deep-menu li a {
  display: block;
  padding: 15px 16px;
  margin: 0;
  color: #333;
  white-space: nowrap;
  transition: color 0.3s, background 0.3s;
}
.deep-menu li a:hover {
  background: #f8f8f8;
  color: #CE1212;
}
/* Book Button */
.book-btn {
  background: #CE1212;
  color: white;
  border: none;
  padding: 6px 20px;
  margin: 0px 15px 0px 0px;
  border-radius: 50px;
  font-size: 14px;
  font-weight: bold;
  cursor: pointer;
  transition: background 0.3s;
}
.book-btn:hover {
  background: #ce1212;
}

/* Transitions */
.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
.nav-links a::before {
  bottom: -4px;
}

/* === Mobile Navigation Styles === */
@media (max-width: 768px) {
  /* Keep header layout in one row */
  .navbar-container {
    padding: 0 15px;
    margin: 0;
  }

  /* Keep logo visible */
  .logo {
    margin-left: 0;
    font-size: 24px;
  }

  /* Hide normal nav links */
  .nav-links {
    display: none;
  }

  /* Show Book button, shrink padding */
  .book-btn {
    padding: 7px 14px;
    font-size: 13px;
  }

  /* Add hamburger menu */
  .hamburger {
    display: block;
    cursor: pointer;
    font-size: 22px;
    background: none;
    border: none;
    color: #37373f;
  }

  /* Make hamburger + logo + button align */
  .navbar-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}

/* By default hamburger is hidden */
.hamburger {
  display: none;
}

/* right side container */
.nav-actions {
  display: flex;
  align-items: center;
}

/* mobile nav */
@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  .nav-links.show-mobile-menu {
    display: block;
    position: absolute;
    top: 85px;
    left: 0;
    width: 100%;
    background: white;
    padding: 20px 0;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  }
  .nav-links.show-mobile-menu ul {
    flex-direction: column;
    gap: 0;
  }
  .nav-links.show-mobile-menu li {
    text-align: center;
    margin: 10px 0;
  }
  .hamburger {
    display: block;
    margin-left: 10px;
    font-size: 22px;
    background: none;
    border: none;
    color: #37373f;
    cursor: pointer;
  }
}
</style> 