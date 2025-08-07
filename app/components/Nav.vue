<template>
  <header class="navbar">
    <div class="navbar-container">
      <div class="logo">Yummy<span class="dot">.</span></div>
<nav class="nav-links">
  <ul>
    <li>
      <a
        href="#index"
        :class="{ active: activeLink === 'index' }"
        @click="setActive('index')"
      >Home</a>
    </li>
    <li>
      <a
        href="#AboutSection"
        :class="{ active: activeLink === 'about' }"
        @click="setActive('about')"
      >About</a>
    </li>
    <li>
      <a
        href="#menu"
        :class="{ active: activeLink === 'menu' }"
        @click="setActive('menu')"
      >Menu</a>
    </li>
    <li>
      <a
        href="#EventsSection"
        :class="{ active: activeLink === 'events' }"
        @click="setActive('events')"
      >Events</a>
    </li>
    <li>
      <a
        href="#ChefSection"
        :class="{ active: activeLink === 'chefs' }"
        @click="setActive('chefs')"
      >Chefs</a>
    </li>
    <li>
      <a
        href="#GallerySection"
        :class="{ active: activeLink === 'gallery' }"
        @click="setActive('gallery')"
      >Gallery</a>
    </li>

    <li class="dropdown" @click="toggleDropdown">
      <a href="#index">Dropdown <i class="fa-solid fa-chevron-down"></i></a>
      <transition name="fade">
        <ul v-show="dropdownOpen" class="dropdown-menu">
          <li><a href="#">Dropdown 1</a></li>
          <li class="deep-dropdown" @click.stop="toggleDeepDropdown">
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

    <li>
      <a
        href="#ContactSection"
        :class="{ active: activeLink === 'contact' }"
        @click="setActive('contact')"
      >Contact</a>
    </li>
  </ul>
</nav>

      <button class="book-btn">Book a Table</button>
    </div>
  </header>
</template>

<script>
export default {
 data() {
  return {
    dropdownOpen: false,
    deepDropdownOpen: false,
    activeLink: 'index', // default active
  };
},
methods: {
  toggleDropdown() {
    this.dropdownOpen = !this.dropdownOpen;
    if (!this.dropdownOpen) this.deepDropdownOpen = false;
  },
  toggleDeepDropdown() {
    this.deepDropdownOpen = !this.deepDropdownOpen;
  },
  setActive(link) {
    this.activeLink = link;
  },
},

};
</script>

<style scoped>
/* Layout */
.navbar {
  background: #fff;
  padding: 12px 40px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  position: fixed;
  width: 100%;
  height: 75px;
  top: 0;
  margin: 0;
  z-index: 1000;
   padding: 20px 0px; 
}
.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 20px;
  margin: 0px 49px;
}

/* Logo */
.logo {
  font-size: 30px;
  font-weight: 700;
  color: #37373f;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
   margin-left: 38px;
   margin-right: 40px;
}
.dot {
  color: #CE1212;
  font-size: 25px;
}

/* Navigation */
.nav-links ul {
  display: flex;
  list-style: none;
  gap: 25px;
  margin-right: -10px;
  padding: 0;
  margin: 0;
}
.nav-links a {
  text-decoration: none;
  margin-left: 20px;
  padding:10px 20px ;
  /* color: #37373f; */
  color: #7f7f90;
 font-size: 15px; 
  font-weight: 500;
  font-family: "Inter", sans-serif;
  /* position: relative; */
  /* display: flex;
  justify-content: space-between;
  align-items: center; */
}

/* Dropdown */
.dropdown {
  position: relative;
  cursor: pointer;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  background: white;
  min-width: 200px;
  display: flex;
  flex-direction: column;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  padding: 0px 50px;
  margin-left: 10px;
  z-index: 100;
  line-height: 1px;
}
.dropdown-menu li {
  position: relative;
}

.dropdown-menu a {
  display: block;
  padding: 4px 20px;
  margin-top: 10px;
  margin-bottom: -2px;
  color: #333;
  white-space: nowrap;
  
}
.dropdown-menu a:hover {
  background: #f8f8f8;
  color: #c0392b;
}

/* Deep Dropdown */
.deep-dropdown {
  position: relative;
}
.deep-menu {
  position: absolute;
  top: 0;
  right: 100%; /* Shows on the left */
  background: white;
  display: flex;
  flex-direction: column;
  min-width: 180px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  z-index: 101;
}
.deep-menu a {
  padding: 3px;
  margin-left: 10px;
  line-height: 2px;
  display: block;
  color: #333;
}
.deep-menu a:hover {
  background: #f8f8f8;
  color: #c0392b;
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
.nav-links a {
  text-decoration: none;
  padding: 10px 0;
  color: #7f7f90;
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
</style>