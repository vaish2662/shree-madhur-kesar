<template>
  <nav class="navbar" :class="{ scrolled: isScrolled }">
    <div class="nav-container">
      <RouterLink class="brand" to="/">
        <span class="brand-icon">🥭</span>
        <div class="brand-text">
          <span class="brand-main">Shree Madhur</span>
          <span class="brand-sub">Kesar Mango</span>
        </div>
      </RouterLink>

      <button class="hamburger" @click="menuOpen = !menuOpen" :class="{ open: menuOpen }">
        <span></span><span></span><span></span>
      </button>

      <ul class="nav-links" :class="{ open: menuOpen }">
        <li v-for="link in links" :key="link.to">
          <RouterLink :to="link.to" @click="menuOpen = false">{{ link.label }}</RouterLink>
        </li>
        <li>
          <a href="https://wa.me/91XXXXXXXXXX" target="_blank" class="nav-cta">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.855L.057 23.882l6.18-1.622A11.94 11.94 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.894a9.87 9.87 0 01-5.031-1.378l-.36-.214-3.733.979.998-3.648-.235-.374A9.862 9.862 0 012.106 12C2.106 6.579 6.579 2.106 12 2.106c5.42 0 9.894 4.473 9.894 9.894 0 5.42-4.474 9.894-9.894 9.894z"/></svg>
            Order Now
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const links = [
  { to: '/', label: 'Home' },
  { to: '/products', label: 'Products' },
  { to: '/about', label: 'About Us' },
  { to: '/contact', label: 'Contact' },
];

const menuOpen = ref(false);
const isScrolled = ref(false);

function handleScroll() {
  isScrolled.value = window.scrollY > 30;
}
onMounted(() => window.addEventListener('scroll', handleScroll));
onUnmounted(() => window.removeEventListener('scroll', handleScroll));
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Nunito:wght@400;600;700&display=swap');

.navbar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  transition: all 0.3s ease;
  padding: 18px 0;
  background: transparent;
}
.navbar.scrolled {
  background: rgba(255, 247, 230, 0.97);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 24px rgba(180,90,0,0.1);
  padding: 12px 0;
}
.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  text-decoration: none;
}
.brand-icon {
  font-size: 2rem;
  filter: drop-shadow(0 2px 4px rgba(0,0,0,0.15));
}
.brand-text {
  display: flex;
  flex-direction: column;
  line-height: 1.1;
}
.brand-main {
  font-family: 'Playfair Display', serif;
  font-weight: 700;
  font-size: 1.15rem;
  color: #1a0a00;
}
.brand-sub {
  font-family: 'Nunito', sans-serif;
  font-size: 0.72rem;
  color: #b45a00;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
.nav-links {
  display: flex;
  align-items: center;
  gap: 8px;
  list-style: none;
  margin: 0; padding: 0;
}
.nav-links li a {
  font-family: 'Nunito', sans-serif;
  font-weight: 600;
  font-size: 0.95rem;
  color: #1a0a00;
  text-decoration: none;
  padding: 8px 14px;
  border-radius: 50px;
  transition: all 0.2s;
}
.nav-links li a:hover,
.nav-links li a.router-link-active {
  background: rgba(180,90,0,0.1);
  color: #b45a00;
}
.nav-cta {
  background: linear-gradient(135deg, #25D366, #128C7E) !important;
  color: white !important;
  padding: 8px 18px !important;
  border-radius: 50px !important;
  display: flex !important;
  align-items: center;
  gap: 7px;
  font-weight: 700 !important;
}
.nav-cta:hover {
  background: linear-gradient(135deg, #1ebe5a, #0f7a6e) !important;
  transform: translateY(-1px);
  box-shadow: 0 4px 16px rgba(37,211,102,0.3);
}
.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}
.hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background: #1a0a00;
  border-radius: 2px;
  transition: all 0.3s;
}
.hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.hamburger.open span:nth-child(2) { opacity: 0; }
.hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

@media (max-width: 768px) {
  .hamburger { display: flex; }
  .nav-links {
    display: none;
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background: rgba(255,247,230,0.98);
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 24px;
    backdrop-filter: blur(16px);
  }
  .nav-links.open { display: flex; }
  .nav-links li a { font-size: 1.3rem; }
}
</style>