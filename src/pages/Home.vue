<template>
  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg">
      <div class="hero-blob blob1"></div>
      <div class="hero-blob blob2"></div>
      <div class="hero-blob blob3"></div>
      <div class="hero-dots"></div>
    </div>
    <div class="hero-content">
      <div class="hero-eyebrow">🌿 Farm to Doorstep · Pune, Maharashtra</div>
      <h1 class="hero-title">
        The Finest<br>
        <span class="hero-accent">Kesar Mangoes</span><br>
        From Our Farm
      </h1>
      <p class="hero-subtitle">
        Naturally ripened, chemical-free, hand-picked with love. 
        Experience the true taste of India's most beloved mango.
      </p>
      <div class="hero-actions">
        <RouterLink to="/products" class="btn-primary">Explore Products</RouterLink>
        <a href="https://wa.me/91XXXXXXXXXX" target="_blank" class="btn-whatsapp">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.855L.057 23.882l6.18-1.622A11.94 11.94 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.894a9.87 9.87 0 01-5.031-1.378l-.36-.214-3.733.979.998-3.648-.235-.374A9.862 9.862 0 012.106 12C2.106 6.579 6.579 2.106 12 2.106c5.42 0 9.894 4.473 9.894 9.894 0 5.42-4.474 9.894-9.894 9.894z"/></svg>
          Chat on WhatsApp
        </a>
      </div>
      <div class="hero-stats">
        <div class="stat">
          <span class="stat-num">15+</span>
          <span class="stat-label">Years of Farming</span>
        </div>
        <div class="stat-divider"></div>
        <div class="stat">
          <span class="stat-num">100%</span>
          <span class="stat-label">Chemical Free</span>
        </div>
        <div class="stat-divider"></div>
        <div class="stat">
          <span class="stat-num">5000+</span>
          <span class="stat-label">Happy Customers</span>
        </div>
      </div>
    </div>
    <div class="hero-visual">
      <div class="hero-mango-wrap">
        <div class="hero-mango-ring ring1"></div>
        <div class="hero-mango-ring ring2"></div>
        <div class="hero-mango-emoji">🥭</div>
        <div class="floating-badge badge-top">GI Tagged ✅</div>
        <div class="floating-badge badge-bottom">Fresh Daily 🌅</div>
      </div>
    </div>
  </section>

  <!-- WHY US -->
  <section class="why-section">
    <div class="container">
      <div class="section-header">
        <div class="section-tag">Why Choose Us</div>
        <h2 class="section-title">Pure. Natural. Delicious.</h2>
      </div>
      <div class="features-grid">
        <div class="feature-card" v-for="f in features" :key="f.icon">
          <div class="feature-icon">{{ f.icon }}</div>
          <h3 class="feature-title">{{ f.title }}</h3>
          <p class="feature-desc">{{ f.desc }}</p>
        </div>
      </div>
    </div>
  </section>

  <!-- PRODUCTS PREVIEW -->
  <section class="products-section">
    <div class="container">
      <div class="section-header">
        <div class="section-tag">Our Products</div>
        <h2 class="section-title">From the Farm, For You</h2>
        <p class="section-subtitle">Fresh mangoes, mango candy, dried slices, and more — all made with love.</p>
      </div>
      <div class="products-grid">
        <ProductCard v-for="p in featuredProducts" :key="p.id" :product="p" />
      </div>
      <div class="products-cta">
        <RouterLink to="/products" class="btn-primary">View All Products →</RouterLink>
      </div>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section class="testimonials-section">
    <div class="container">
      <div class="section-header">
        <div class="section-tag">Customer Love</div>
        <h2 class="section-title">What Our Customers Say</h2>
      </div>
      <div class="testimonials-grid">
        <div class="testimonial-card" v-for="t in testimonials" :key="t.name">
          <div class="testimonial-stars">★★★★★</div>
          <p class="testimonial-text">"{{ t.text }}"</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">{{ t.name[0] }}</div>
            <div>
              <div class="testimonial-name">{{ t.name }}</div>
              <div class="testimonial-location">{{ t.location }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CTA BANNER -->
  <section class="cta-section">
    <div class="cta-content">
      <h2 class="cta-title">Ready to taste the difference?</h2>
      <p class="cta-subtitle">Order directly on WhatsApp. Fresh mangoes delivered to your door.</p>
      <a href="https://wa.me/91XXXXXXXXXX?text=Hello! I'd like to place an order for fresh Kesar mangoes." target="_blank" class="cta-btn">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.855L.057 23.882l6.18-1.622A11.94 11.94 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.894a9.87 9.87 0 01-5.031-1.378l-.36-.214-3.733.979.998-3.648-.235-.374A9.862 9.862 0 012.106 12C2.106 6.579 6.579 2.106 12 2.106c5.42 0 9.894 4.473 9.894 9.894 0 5.42-4.474 9.894-9.894 9.894z"/></svg>
        Order on WhatsApp Now
      </a>
    </div>
  </section>
</template>

<script setup>
import ProductCard from '../components/ProductCard.vue';    
import products from '../data/product';

const featuredProducts = products.slice(0, 3);

const features = [
  { icon: '🌿', title: 'Chemical Free', desc: 'Our mangoes are grown without any harmful chemicals or artificial ripening agents.' },
  { icon: '☀️', title: 'Naturally Ripened', desc: 'Every mango is allowed to ripen naturally on the tree for maximum sweetness.' },
  { icon: '🚚', title: 'Direct Delivery', desc: 'From our farm straight to your home. No middlemen, no delays, just freshness.' },
  { icon: '🏆', title: 'Premium Quality', desc: 'Hand-picked and graded to ensure only the best mangoes reach your table.' },
  { icon: '👨‍🌾', title: 'Family Farm', desc: 'A family-owned orchard with over 15 years of passion for quality mangoes.' },
  { icon: '💚', title: 'Eco-Friendly', desc: 'Sustainable farming practices that respect nature and the environment.' },
];

const testimonials = [
  { name: 'Priya Sharma', location: 'Pune', text: 'The Kesar mangoes are absolutely divine! The flavour is incomparable to anything I\'ve bought from a market. Will order every season.' },
  { name: 'Rahul Mehta', location: 'Mumbai', text: 'Ordered the gift box for Diwali and my family loved it. The dried mango slices are addictive! Fresh and natural, just as promised.' },
  { name: 'Sunita Joshi', location: 'Nashik', text: 'The mango candy (aam papad) takes me back to my childhood. Pure Kesar taste, no artificial flavours. Highly recommend!' },
];
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&family=Nunito:wght@400;600;700&display=swap');

* { box-sizing: border-box; }

/* HERO */
.hero {
  min-height: 100vh;
  background: linear-gradient(135deg, #fff8ee 0%, #fff3d6 50%, #ffe8b3 100%);
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  padding: 100px 64px 60px;
  position: relative;
  overflow: hidden;
  gap: 40px;
}
.hero-bg { position: absolute; inset: 0; pointer-events: none; }
.hero-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(60px);
  opacity: 0.4;
}
.blob1 { width: 400px; height: 400px; background: #ffd166; top: -100px; right: 100px; animation: float1 8s ease-in-out infinite; }
.blob2 { width: 300px; height: 300px; background: #ff9f43; bottom: -50px; left: 200px; animation: float2 10s ease-in-out infinite; }
.blob3 { width: 200px; height: 200px; background: #ffeaa7; top: 50%; right: 300px; animation: float1 12s ease-in-out infinite reverse; }

.hero-dots {
  position: absolute; inset: 0;
  background-image: radial-gradient(circle, rgba(180,90,0,0.08) 1px, transparent 1px);
  background-size: 32px 32px;
}

@keyframes float1 { 0%,100% { transform: translateY(0) scale(1); } 50% { transform: translateY(-30px) scale(1.05); } }
@keyframes float2 { 0%,100% { transform: translateY(0) rotate(0deg); } 50% { transform: translateY(-20px) rotate(5deg); } }

.hero-content { position: relative; z-index: 2; }
.hero-eyebrow {
  display: inline-block;
  font-family: 'Nunito', sans-serif;
  font-size: 0.85rem;
  font-weight: 700;
  color: #b45a00;
  background: rgba(180,90,0,0.1);
  border: 1px solid rgba(180,90,0,0.2);
  padding: 6px 16px;
  border-radius: 50px;
  letter-spacing: 0.05em;
  margin-bottom: 24px;
}
.hero-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.4rem, 5vw, 3.8rem);
  font-weight: 700;
  color: #1a0a00;
  line-height: 1.15;
  margin: 0 0 20px;
}
.hero-accent {
  color: #e07b00;
  font-style: italic;
}
.hero-subtitle {
  font-family: 'Nunito', sans-serif;
  font-size: 1.1rem;
  color: #5a3a1a;
  line-height: 1.7;
  margin: 0 0 36px;
  max-width: 480px;
}
.hero-actions { display: flex; gap: 14px; flex-wrap: wrap; margin-bottom: 48px; }

.btn-primary {
  display: inline-flex;
  align-items: center;
  padding: 14px 28px;
  background: linear-gradient(135deg, #e07b00, #c45e00);
  color: white;
  border-radius: 50px;
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  font-size: 1rem;
  text-decoration: none;
  transition: all 0.25s;
  box-shadow: 0 6px 24px rgba(224,123,0,0.35);
}
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 10px 32px rgba(224,123,0,0.45); }

.btn-whatsapp {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 28px;
  background: linear-gradient(135deg, #25D366, #128C7E);
  color: white;
  border-radius: 50px;
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  font-size: 1rem;
  text-decoration: none;
  transition: all 0.25s;
  box-shadow: 0 6px 24px rgba(37,211,102,0.3);
}
.btn-whatsapp:hover { transform: translateY(-2px); box-shadow: 0 10px 32px rgba(37,211,102,0.4); }

.hero-stats { display: flex; align-items: center; gap: 28px; }
.stat { text-align: center; }
.stat-num { display: block; font-family: 'Playfair Display', serif; font-size: 1.6rem; font-weight: 700; color: #1a0a00; }
.stat-label { font-family: 'Nunito', sans-serif; font-size: 0.75rem; color: #7a5030; letter-spacing: 0.05em; text-transform: uppercase; }
.stat-divider { width: 1px; height: 40px; background: rgba(180,90,0,0.2); }

.hero-visual {
  position: relative;
  z-index: 2;
  display: flex;
  align-items: center;
  justify-content: center;
}
.hero-mango-wrap {
  position: relative;
  width: 360px;
  height: 360px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.hero-mango-ring {
  position: absolute;
  border-radius: 50%;
  border: 2px dashed rgba(180,90,0,0.2);
  animation: spin 20s linear infinite;
}
.ring1 { width: 320px; height: 320px; }
.ring2 { width: 260px; height: 260px; animation-direction: reverse; border-color: rgba(224,123,0,0.15); }
@keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
.hero-mango-emoji {
  font-size: 9rem;
  filter: drop-shadow(0 20px 40px rgba(180,90,0,0.25));
  animation: float1 6s ease-in-out infinite;
}
.floating-badge {
  position: absolute;
  background: white;
  border-radius: 50px;
  padding: 8px 18px;
  font-family: 'Nunito', sans-serif;
  font-size: 0.85rem;
  font-weight: 700;
  color: #1a0a00;
  box-shadow: 0 8px 24px rgba(0,0,0,0.12);
}
.badge-top { top: 40px; right: 10px; animation: float2 5s ease-in-out infinite; }
.badge-bottom { bottom: 40px; left: 10px; animation: float1 7s ease-in-out infinite; }

/* SECTIONS */
.container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
.section-header { text-align: center; margin-bottom: 56px; }
.section-tag {
  display: inline-block;
  font-family: 'Nunito', sans-serif;
  font-size: 0.8rem;
  font-weight: 700;
  color: #b45a00;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  background: rgba(180,90,0,0.08);
  padding: 6px 16px;
  border-radius: 50px;
  margin-bottom: 14px;
}
.section-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.8rem, 3.5vw, 2.8rem);
  font-weight: 700;
  color: #1a0a00;
  margin: 0 0 12px;
}
.section-subtitle {
  font-family: 'Nunito', sans-serif;
  color: #7a5030;
  font-size: 1rem;
  margin: 0;
}

/* WHY US */
.why-section { padding: 96px 0; background: #fff; }
.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 28px;
}
.feature-card {
  padding: 32px 28px;
  border-radius: 20px;
  background: linear-gradient(135deg, #fff8ee, #fff3d6);
  border: 1px solid rgba(180,90,0,0.1);
  transition: all 0.3s;
}
.feature-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 40px rgba(180,90,0,0.1);
}
.feature-icon { font-size: 2.2rem; margin-bottom: 16px; }
.feature-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.15rem;
  font-weight: 700;
  color: #1a0a00;
  margin: 0 0 10px;
}
.feature-desc {
  font-family: 'Nunito', sans-serif;
  color: #7a5030;
  font-size: 0.9rem;
  line-height: 1.6;
  margin: 0;
}

/* PRODUCTS */
.products-section { padding: 96px 0; background: #fdf6ec; }
.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 28px;
  margin-bottom: 48px;
}
.products-cta { text-align: center; }

/* TESTIMONIALS */
.testimonials-section { padding: 96px 0; background: #fff; }
.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 28px;
}
.testimonial-card {
  padding: 32px 28px;
  border-radius: 20px;
  border: 1px solid rgba(180,90,0,0.12);
  background: #fff;
  transition: all 0.3s;
}
.testimonial-card:hover { box-shadow: 0 12px 40px rgba(180,90,0,0.1); transform: translateY(-3px); }
.testimonial-stars { color: #ffd166; font-size: 1.1rem; margin-bottom: 16px; letter-spacing: 2px; }
.testimonial-text {
  font-family: 'Nunito', sans-serif;
  color: #3a2010;
  font-size: 0.95rem;
  line-height: 1.7;
  margin: 0 0 20px;
  font-style: italic;
}
.testimonial-author { display: flex; align-items: center; gap: 12px; }
.testimonial-avatar {
  width: 42px; height: 42px;
  border-radius: 50%;
  background: linear-gradient(135deg, #e07b00, #ffd166);
  color: white;
  display: flex; align-items: center; justify-content: center;
  font-family: 'Playfair Display', serif;
  font-weight: 700;
  font-size: 1.1rem;
}
.testimonial-name {
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  color: #1a0a00;
  font-size: 0.95rem;
}
.testimonial-location {
  font-family: 'Nunito', sans-serif;
  color: #7a5030;
  font-size: 0.8rem;
}

/* CTA */
.cta-section {
  padding: 96px 24px;
  background: linear-gradient(135deg, #1a0a00 0%, #3a1800 100%);
  text-align: center;
  position: relative;
  overflow: hidden;
}
.cta-section::before {
  content: '🥭🥭🥭';
  position: absolute;
  font-size: 8rem;
  opacity: 0.05;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  white-space: nowrap;
  letter-spacing: 40px;
}
.cta-content { position: relative; z-index: 1; }
.cta-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.8rem, 4vw, 3rem);
  font-weight: 700;
  color: #ffd166;
  margin: 0 0 16px;
}
.cta-subtitle {
  font-family: 'Nunito', sans-serif;
  color: #c4956a;
  font-size: 1.05rem;
  margin: 0 0 36px;
}
.cta-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 16px 36px;
  background: linear-gradient(135deg, #25D366, #128C7E);
  color: white;
  border-radius: 50px;
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  font-size: 1.1rem;
  text-decoration: none;
  transition: all 0.25s;
  box-shadow: 0 8px 32px rgba(37,211,102,0.3);
}
.cta-btn:hover { transform: translateY(-2px); box-shadow: 0 12px 40px rgba(37,211,102,0.4); }

/* RESPONSIVE */
@media (max-width: 900px) {
  .hero {
    grid-template-columns: 1fr;
    padding: 100px 24px 60px;
    text-align: center;
  }
  .hero-subtitle { margin: 0 auto 36px; }
  .hero-actions { justify-content: center; }
  .hero-stats { justify-content: center; }
  .hero-visual { display: none; }
}
</style>