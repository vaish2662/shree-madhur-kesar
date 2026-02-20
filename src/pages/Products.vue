<template>
  <div class="products-page">
    <!-- Page Header -->
    <div class="page-header">
      <div class="header-bg">
        <div class="h-blob hb1"></div>
        <div class="h-blob hb2"></div>
      </div>
      <div class="header-content">
        <div class="breadcrumb">
          <RouterLink to="/">Home</RouterLink> / <span>Products</span>
        </div>
        <h1 class="page-title">Our Mango Products</h1>
        <p class="page-subtitle">From fresh Kesar mangoes to dried treats — pure, natural, and straight from our farm.</p>
      </div>
    </div>

    <!-- Filter Tabs -->
    <div class="filter-bar">
      <div class="filter-container">
        <button
          v-for="cat in categories"
          :key="cat"
          class="filter-btn"
          :class="{ active: activeCategory === cat }"
          @click="activeCategory = cat"
        >{{ cat }}</button>
      </div>
    </div>

    <!-- Products Grid -->
    <section class="products-section">
      <div class="container">
        <div class="products-grid">
          <ProductCard v-for="p in filteredProducts" :key="p.id" :product="p" />
        </div>
        <div v-if="filteredProducts.length === 0" class="no-products">
          <span>😔</span> No products in this category yet.
        </div>
      </div>
    </section>

    <!-- Bulk Order Banner -->
    <section class="bulk-section">
      <div class="bulk-card">
        <div class="bulk-icon">📦</div>
        <div class="bulk-text">
          <h3>Bulk & Corporate Orders</h3>
          <p>Looking to order in bulk for your office, event, or gifting? We offer special pricing for large orders. Get in touch!</p>
        </div>
        <a href="https://wa.me/91XXXXXXXXXX?text=Hello! I'm interested in placing a bulk order for mangoes." target="_blank" class="bulk-btn">
          Request Bulk Quote
        </a>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import ProductCard from '../components/ProductCard.vue';
import products from '../data/product';

const categories = ['All', ...new Set(products.map(p => p.category))];
const activeCategory = ref('All');

const filteredProducts = computed(() =>
  activeCategory.value === 'All' ? products : products.filter(p => p.category === activeCategory.value)
);
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Nunito:wght@400;600;700&display=swap');

.products-page { background: #fdf6ec; }

/* PAGE HEADER */
.page-header {
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #fff8ee, #ffe8b3);
  padding: 120px 24px 72px;
  text-align: center;
}
.header-bg { position: absolute; inset: 0; pointer-events: none; }
.h-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(50px);
  opacity: 0.5;
}
.hb1 { width: 300px; height: 300px; background: #ffd166; top: -80px; right: 10%; }
.hb2 { width: 200px; height: 200px; background: #ffb347; bottom: -50px; left: 15%; }

.header-content { position: relative; z-index: 1; }
.breadcrumb {
  font-family: 'Nunito', sans-serif;
  font-size: 0.85rem;
  color: #7a5030;
  margin-bottom: 16px;
}
.breadcrumb a { color: #b45a00; text-decoration: none; }
.breadcrumb a:hover { text-decoration: underline; }
.page-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2rem, 5vw, 3.2rem);
  color: #1a0a00;
  margin: 0 0 16px;
}
.page-subtitle {
  font-family: 'Nunito', sans-serif;
  color: #5a3a1a;
  font-size: 1.05rem;
  max-width: 500px;
  margin: 0 auto;
  line-height: 1.6;
}

/* FILTER */
.filter-bar {
  position: sticky;
  top: 70px;
  z-index: 100;
  background: rgba(253,246,236,0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(180,90,0,0.1);
  padding: 16px 24px;
}
.filter-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  justify-content: center;
}
.filter-btn {
  padding: 8px 20px;
  border: 1.5px solid rgba(180,90,0,0.25);
  background: transparent;
  border-radius: 50px;
  font-family: 'Nunito', sans-serif;
  font-weight: 600;
  font-size: 0.9rem;
  color: #7a5030;
  cursor: pointer;
  transition: all 0.2s;
}
.filter-btn:hover { border-color: #e07b00; color: #e07b00; }
.filter-btn.active {
  background: linear-gradient(135deg, #e07b00, #c45e00);
  border-color: transparent;
  color: white;
  box-shadow: 0 4px 16px rgba(224,123,0,0.3);
}

/* PRODUCTS */
.products-section { padding: 64px 0 80px; }
.container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 28px;
}
.no-products {
  text-align: center;
  padding: 80px;
  font-family: 'Nunito', sans-serif;
  color: #7a5030;
  font-size: 1.1rem;
}

/* BULK */
.bulk-section { padding: 0 24px 80px; }
.bulk-card {
  max-width: 1200px;
  margin: 0 auto;
  background: linear-gradient(135deg, #1a0a00, #3a1800);
  border-radius: 24px;
  padding: 48px;
  display: flex;
  align-items: center;
  gap: 32px;
  flex-wrap: wrap;
}
.bulk-icon { font-size: 3rem; flex-shrink: 0; }
.bulk-text { flex: 1; min-width: 220px; }
.bulk-text h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  color: #ffd166;
  margin: 0 0 8px;
}
.bulk-text p {
  font-family: 'Nunito', sans-serif;
  color: #c4956a;
  margin: 0;
  line-height: 1.6;
}
.bulk-btn {
  padding: 14px 28px;
  background: linear-gradient(135deg, #e07b00, #c45e00);
  color: white;
  border-radius: 50px;
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  text-decoration: none;
  white-space: nowrap;
  transition: all 0.2s;
  box-shadow: 0 6px 20px rgba(224,123,0,0.4);
}
.bulk-btn:hover { transform: translateY(-2px); box-shadow: 0 10px 28px rgba(224,123,0,0.5); }

@media (max-width: 600px) {
  .bulk-card { flex-direction: column; text-align: center; }
  .products-grid { grid-template-columns: 1fr; }
}
</style>