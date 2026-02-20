<template>
  <div class="card" @mouseenter="hovered = true" @mouseleave="hovered = false">
    <div class="card-img-wrap">
      <img :src="product.image" :alt="product.name" class="card-img" />
      <div class="card-badge" v-if="product.badge">{{ product.badge }}</div>
      <div class="card-overlay" :class="{ show: hovered }">
        <p class="card-desc">{{ product.description }}</p>
      </div>
    </div>
    <div class="card-body">
      <div class="card-tag">{{ product.category }}</div>
      <h3 class="card-title">{{ product.name }}</h3>
      <div class="card-price">{{ product.price }}</div>
      <a :href="whatsappLink" target="_blank" class="card-btn">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.855L.057 23.882l6.18-1.622A11.94 11.94 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.894a9.87 9.87 0 01-5.031-1.378l-.36-.214-3.733.979.998-3.648-.235-.374A9.862 9.862 0 012.106 12C2.106 6.579 6.579 2.106 12 2.106c5.42 0 9.894 4.473 9.894 9.894 0 5.42-4.474 9.894-9.894 9.894z"/></svg>
        Order on WhatsApp
      </a>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const props = defineProps({ product: Object });
const hovered = ref(false);
const whatsappLink = `https://wa.me/91XXXXXXXXXX?text=${encodeURIComponent(`Hello! I'd like to order ${props.product.name} (${props.product.price}). Please confirm availability.`)}`;
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Nunito:wght@400;600;700&display=swap');

.card {
  border-radius: 20px;
  overflow: hidden;
  background: #fff;
  box-shadow: 0 4px 24px rgba(180,90,0,0.08);
  transition: all 0.35s cubic-bezier(.22,.68,0,1.2);
  cursor: pointer;
}
.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 16px 48px rgba(180,90,0,0.18);
}
.card-img-wrap {
  position: relative;
  overflow: hidden;
  height: 240px;
}
.card-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}
.card:hover .card-img { transform: scale(1.07); }
.card-badge {
  position: absolute;
  top: 14px; left: 14px;
  background: #ff6b35;
  color: white;
  font-family: 'Nunito', sans-serif;
  font-size: 0.75rem;
  font-weight: 700;
  padding: 4px 12px;
  border-radius: 50px;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}
.card-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(26,10,0,0.85) 0%, transparent 60%);
  display: flex;
  align-items: flex-end;
  padding: 20px;
  opacity: 0;
  transition: opacity 0.3s;
}
.card-overlay.show { opacity: 1; }
.card-desc {
  color: #ffe8c0;
  font-family: 'Nunito', sans-serif;
  font-size: 0.9rem;
  margin: 0;
  line-height: 1.5;
}
.card-body {
  padding: 20px 22px 24px;
}
.card-tag {
  font-family: 'Nunito', sans-serif;
  font-size: 0.72rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: #b45a00;
  margin-bottom: 6px;
}
.card-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.25rem;
  font-weight: 700;
  color: #1a0a00;
  margin: 0 0 8px;
}
.card-price {
  font-family: 'Nunito', sans-serif;
  font-size: 1.05rem;
  font-weight: 700;
  color: #e07b00;
  margin-bottom: 16px;
}
.card-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  width: 100%;
  padding: 12px;
  background: linear-gradient(135deg, #25D366, #128C7E);
  color: white;
  border-radius: 12px;
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  font-size: 0.95rem;
  text-decoration: none;
  transition: all 0.2s;
}
.card-btn:hover {
  background: linear-gradient(135deg, #1ebe5a, #0f7a6e);
  transform: translateY(-1px);
  box-shadow: 0 6px 20px rgba(37,211,102,0.35);
}
</style>