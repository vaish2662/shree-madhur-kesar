<template>
  <footer class="footer">
    <div class="footer-inner">
      <div class="footer-brand">
        <span class="footer-mango">🥭</span>
        <div>
          <div class="footer-name">Shree Madhur Kesar Mango</div>
          <div class="footer-tagline">Naturally ripened. Delivered with love.</div>
        </div>
      </div>
      <div class="footer-links">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/products">Products</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
      </div>
      <div class="footer-copy">© {{ new Date().getFullYear() }} Shree Madhur Kesar Mango · Nanded, Maharashtra 🍃</div>
    </div>
  </footer>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Nunito:wght@400;600&display=swap');

.footer {
  background: #1a0a00;
  color: #fff8ee;
  padding: 48px 24px 28px;
}
.footer-inner {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 28px;
  text-align: center;
}
.footer-brand {
  display: flex;
  align-items: center;
  gap: 14px;
}
.footer-mango { font-size: 2.5rem; }
.footer-name {
  font-family: 'Playfair Display', serif;
  font-size: 1.15rem;
  font-weight: 700;
  color: #ffd166;
}
.footer-tagline {
  font-family: 'Nunito', sans-serif;
  font-size: 0.85rem;
  color: #c4956a;
  margin-top: 2px;
}
.footer-links {
  display: flex;
  gap: 24px;
  flex-wrap: wrap;
  justify-content: center;
}
.footer-links a {
  font-family: 'Nunito', sans-serif;
  font-size: 0.9rem;
  color: #c4956a;
  text-decoration: none;
  transition: color 0.2s;
}
.footer-links a:hover { color: #ffd166; }
.footer-copy {
  font-family: 'Nunito', sans-serif;
  font-size: 0.8rem;
  color: #6b4c30;
  border-top: 1px solid #2e1800;
  width: 100%;
  padding-top: 20px;
}
</style>