<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const navItems = [
  { label: 'Home', id: 'home' },
  { label: 'About', id: 'about' },
  { label: 'Skills', id: 'skills' },
  { label: 'Experience', id: 'experience' },
  { label: 'Portfolio', id: 'portfolio' },
  { label: 'Education', id: 'education' },
  { label: 'Contact', id: 'contact' }
]

const handleNavClick = (itemId) => {
  isMenuOpen.value = false
  const element = document.getElementById(itemId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <nav class="navbar-aesthetic">
    <div class="navbar-container">
      <div class="navbar-logo">AW</div>
      
      <button class="navbar-toggle" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </button>
      
      <ul class="nav-menu" :class="{ active: isMenuOpen }">
        <li v-for="item in navItems" :key="item.id" class="nav-item">
          <a 
            class="nav-link" 
            @click.prevent="handleNavClick(item.id)"
            href="#"
          >
            {{ item.label }}
          </a>
        </li>
      </ul>
      
      <a href="/WJMASHLEY_Resume.pdf" download="Ashley_Wong_Resume.pdf" class="resume-btn text-decoration-none">
        <span class="download-icon">⬇</span> Resume
      </a>
    </div>
  </nav>
</template>

<style scoped>
.navbar-aesthetic {
  background-color: #e6e5d5; /* Matches the page background to be seamless */
  padding: 1.5rem 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  /* Removed the box-shadow so it blends perfectly */
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar-logo {
  font-size: 1.8rem;
  font-weight: bold;
  color: #994d47; /* Rust Brown */
  letter-spacing: 2px;
  font-family: 'Playfair Display', serif;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: 0;
  padding: 0;
  align-items: center;
}

.nav-item {
  margin: 0;
}

.nav-link {
  color: #994d47; /* Rust Brown */
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 500;
  transition: opacity 0.3s ease;
  position: relative;
}

.nav-link:hover {
  opacity: 0.6;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #994d47;
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

.resume-btn {
  background: #994d47; /* Rust Brown */
  color: #e6e5d5; /* Mint Green */
  border: none;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  cursor: pointer;
  font-weight: 600;
  font-size: 0.95rem;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.resume-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(153, 77, 71, 0.3); /* Rust shadow */
  color: #ffffff;
}

.navbar-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  flex-direction: column;
  gap: 5px;
}

.navbar-toggle span {
  width: 25px;
  height: 3px;
  background-color: #994d47; /* Rust Brown hamburger lines */
  border-radius: 2px;
  transition: all 0.3s ease;
}

@media (max-width: 768px) {
  .navbar-toggle { display: flex; }
  .nav-menu {
    position: absolute;
    left: -100%;
    top: 70px;
    flex-direction: column;
    background-color: #e6e5d5; /* Seamless mobile menu */
    width: 100%;
    text-align: center;
    transition: 0.3s;
    padding: 2rem 0;
    gap: 1rem;
    box-shadow: 0 10px 10px rgba(0,0,0,0.05);
  }
  .nav-menu.active { left: 0; }
  .resume-btn { display: none; }
  .navbar-container { padding: 0 1rem; }
}
</style>
