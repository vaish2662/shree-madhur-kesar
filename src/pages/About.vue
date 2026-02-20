<template>
  <div class="about-page">
    <!-- Hero -->
    <div class="about-hero">
      <div class="about-hero-bg">
        <div class="a-blob ab1"></div>
        <div class="a-blob ab2"></div>
      </div>
      <div class="about-hero-content">
        <div class="section-tag">Our Story</div>
        <h1 class="about-title">A Family Rooted<br>in <span class="accent">Mango Love</span></h1>
        <p class="about-lead">
          Since 2008, the Shree Madhur family has been growing the finest Kesar mangoes from our farm in 
          Nanded, Maharashtra — delivering the authentic taste of India directly to your home.
        </p>
      </div>
      <div class="about-hero-visual">
        <div class="emoji-stack">
          <div class="emoji-item e1">🥭</div>
          <div class="emoji-item e2">👨‍🌾</div>
          <div class="emoji-item e3">🌳</div>
        </div>
      </div>
    </div>

    <!-- Story -->
    <section class="story-section">
      <div class="container">
        <div class="story-grid">
          <div class="story-content">
            <div class="section-tag-alt">Who We Are</div>
            <h2 class="story-title">From Our Orchard to Your Table</h2>
            <p class="story-text">
              Shree Madhur Kesar Mango is a family-owned orchard rooted in <strong>Nanded, Maharashtra</strong>.
              Our trees gave us their very first fruit in <strong>2008</strong> — a moment our family still 
              cherishes. By <strong>2010</strong>, we began selling those mangoes directly from our home 
              in Nanded, farm fresh with no middlemen and no compromise on quality.
            </p>
            <p class="story-text">
              Our philosophy has always been simple: grow mangoes the way nature intended. No artificial 
              ripening, no harmful chemicals — just Nanded sun, rich soil, and patience. Every mango is 
              hand-picked at peak ripeness for the richest flavour and saffron aroma Kesar mangoes are famous for.
            </p>
            <p class="story-text">
              Over the years, word spread far beyond Nanded. Today we deliver all across Maharashtra, 
              with our largest customer bases in <strong>Hyderabad</strong> and <strong>Pune</strong>. 
              We also offer traditional mango treats — Aam Papad, dried mango slices, and fresh pulp — 
              bringing the taste of our farm to you year-round.
            </p>
          </div>
          <div class="story-cards">
            <div class="story-card" v-for="val in values" :key="val.icon">
              <div class="story-icon">{{ val.icon }}</div>
              <h4>{{ val.title }}</h4>
              <p>{{ val.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Timeline -->
    <section class="timeline-section">
      <div class="container">
        <div class="section-header">
          <div class="section-tag">Our Journey</div>
          <h2 class="section-title">Growing Together</h2>
        </div>
        <div class="timeline">
          <div class="timeline-item" v-for="(item, i) in timeline" :key="i" :class="{ right: i % 2 !== 0 }">
            <div class="timeline-content">
              <div class="timeline-year">{{ item.year }}</div>
              <h4 class="timeline-event">{{ item.event }}</h4>
              <p class="timeline-desc">{{ item.desc }}</p>
            </div>
            <div class="timeline-dot">{{ item.icon }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA -->
    <section class="about-cta">
      <div class="cta-content">
        <h2>Taste the difference of farm-fresh mangoes</h2>
        <RouterLink to="/products" class="btn-orange">Browse Our Products</RouterLink>
        <RouterLink to="/contact" class="btn-outline">Get in Touch</RouterLink>
      </div>
    </section>
  </div>
</template>

<script setup>
const values = [
  { icon: '🌿', title: 'No Chemicals', desc: '100% natural farming with no pesticides or artificial ripening.' },
  { icon: '❤️', title: 'Family Values', desc: 'Every mango is grown and packed with love and care.' },
  { icon: '🤝', title: 'Trust', desc: 'Thousands of happy families trust us season after season.' },
];

const timeline = [
  { year: '2008', event: 'First Fruit from Our Farm', desc: 'Our Kesar mango trees bore their very first fruit in Nanded — a proud moment that marked the beginning of our journey.', icon: '🌱' },
  { year: '2010', event: 'Started Selling Mangoes', desc: 'We began selling our Kesar mangoes directly from our home in Nanded. Farm fresh, no middlemen, straight from our hands to yours.', icon: '🥭' },
  { year: '2015', event: 'Growing Beyond Nanded', desc: 'Word spread about our naturally ripened, chemical-free mangoes and we started reaching customers across Nanded and neighbouring districts.', icon: '🥳' },
  { year: '2018', event: 'Expanded to Pune & Hyderabad', desc: 'Demand grew fast. We began regularly supplying fresh Kesar mangoes to customers in Pune and Hyderabad — now our two biggest markets.', icon: '🚚' },
  { year: '2021', event: 'Mango Treats Launched', desc: 'We launched Aam Papad, dried mango slices, and fresh pulp to bring the Kesar mango experience to customers year-round.', icon: '🍬' },
  { year: '2024', event: 'All-Maharashtra Delivery', desc: 'Today we deliver across all of Maharashtra. Our heart remains in Nanded, but our mangoes reach every corner of the state and beyond.', icon: '🌟' },
];
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&family=Nunito:wght@400;600;700&display=swap');

.about-page { background: #fdf6ec; }

/* HERO */
.about-hero {
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #fff8ee, #ffe8b3);
  padding: 120px 64px 80px;
  display: grid;
  grid-template-columns: 1fr auto;
  align-items: center;
  gap: 48px;
}
.about-hero-bg { position: absolute; inset: 0; pointer-events: none; }
.a-blob { position: absolute; border-radius: 50%; filter: blur(50px); opacity: 0.45; }
.ab1 { width: 350px; height: 350px; background: #ffd166; top: -100px; right: 5%; }
.ab2 { width: 200px; height: 200px; background: #ff9f43; bottom: -60px; left: 30%; }
.about-hero-content { position: relative; z-index: 1; }

.section-tag {
  display: inline-block;
  font-family: 'Nunito', sans-serif;
  font-size: 0.8rem;
  font-weight: 700;
  color: #b45a00;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  background: rgba(180,90,0,0.1);
  padding: 6px 16px;
  border-radius: 50px;
  margin-bottom: 16px;
}
.section-tag-alt {
  display: inline-block;
  font-family: 'Nunito', sans-serif;
  font-size: 0.8rem;
  font-weight: 700;
  color: #b45a00;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  margin-bottom: 12px;
}
.about-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2rem, 4.5vw, 3.4rem);
  font-weight: 700;
  color: #1a0a00;
  margin: 0 0 20px;
  line-height: 1.2;
}
.accent { color: #e07b00; font-style: italic; }
.about-lead {
  font-family: 'Nunito', sans-serif;
  font-size: 1.05rem;
  color: #5a3a1a;
  max-width: 540px;
  line-height: 1.7;
  margin: 0;
}
.about-hero-visual { position: relative; z-index: 1; }
.emoji-stack {
  display: flex;
  gap: 12px;
  align-items: flex-end;
}
.emoji-item {
  font-size: 5rem;
  filter: drop-shadow(0 8px 20px rgba(0,0,0,0.1));
  animation: float 5s ease-in-out infinite;
}
.e2 { animation-delay: -1.5s; font-size: 6rem; }
.e3 { animation-delay: -3s; }
@keyframes float { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-16px); } }

/* STORY */
.story-section { padding: 96px 0; background: #fff; }
.container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
.story-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 64px;
  align-items: start;
}
.story-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.6rem, 3vw, 2.4rem);
  color: #1a0a00;
  margin: 0 0 24px;
}
.story-text {
  font-family: 'Nunito', sans-serif;
  color: #5a3a1a;
  font-size: 1rem;
  line-height: 1.75;
  margin: 0 0 16px;
}
.story-cards { display: flex; flex-direction: column; gap: 20px; }
.story-card {
  padding: 24px;
  border-radius: 16px;
  background: linear-gradient(135deg, #fff8ee, #fff3d6);
  border: 1px solid rgba(180,90,0,0.1);
}
.story-icon { font-size: 1.8rem; margin-bottom: 10px; }
.story-card h4 {
  font-family: 'Playfair Display', serif;
  font-size: 1.05rem;
  color: #1a0a00;
  margin: 0 0 6px;
}
.story-card p {
  font-family: 'Nunito', sans-serif;
  color: #7a5030;
  font-size: 0.88rem;
  margin: 0;
  line-height: 1.6;
}

/* TIMELINE */
.timeline-section { padding: 96px 0; background: #fdf6ec; }
.section-header { text-align: center; margin-bottom: 64px; }
.section-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.8rem, 3.5vw, 2.6rem);
  color: #1a0a00;
  margin: 0;
}
.timeline {
  position: relative;
  max-width: 700px;
  margin: 0 auto;
}
.timeline::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 0; bottom: 0;
  width: 2px;
  background: linear-gradient(to bottom, #ffd166, #e07b00);
  transform: translateX(-50%);
}
.timeline-item {
  display: flex;
  justify-content: flex-end;
  padding-right: calc(50% + 32px);
  margin-bottom: 48px;
  position: relative;
}
.timeline-item.right {
  justify-content: flex-start;
  padding-right: 0;
  padding-left: calc(50% + 32px);
}
.timeline-content {
  max-width: 280px;
  background: #fff;
  border-radius: 16px;
  padding: 20px 24px;
  box-shadow: 0 4px 20px rgba(180,90,0,0.08);
}
.timeline-year {
  font-family: 'Playfair Display', serif;
  font-size: 1.4rem;
  font-weight: 700;
  color: #e07b00;
  margin-bottom: 4px;
}
.timeline-event {
  font-family: 'Playfair Display', serif;
  font-size: 1rem;
  color: #1a0a00;
  margin: 0 0 6px;
}
.timeline-desc {
  font-family: 'Nunito', sans-serif;
  color: #7a5030;
  font-size: 0.88rem;
  margin: 0;
  line-height: 1.6;
}
.timeline-dot {
  position: absolute;
  left: 50%;
  top: 18px;
  transform: translateX(-50%);
  width: 44px; height: 44px;
  border-radius: 50%;
  background: white;
  border: 2px solid #e07b00;
  display: flex; align-items: center; justify-content: center;
  font-size: 1.2rem;
  box-shadow: 0 4px 12px rgba(224,123,0,0.2);
}

/* CTA */
.about-cta {
  padding: 96px 24px;
  background: linear-gradient(135deg, #1a0a00, #3a1800);
  text-align: center;
}
.cta-content h2 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.6rem, 3.5vw, 2.6rem);
  color: #ffd166;
  margin: 0 0 32px;
}
.cta-content { display: flex; flex-direction: column; align-items: center; gap: 16px; }
.btn-orange {
  padding: 14px 32px;
  background: linear-gradient(135deg, #e07b00, #c45e00);
  color: white;
  border-radius: 50px;
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  text-decoration: none;
  transition: all 0.2s;
  box-shadow: 0 6px 20px rgba(224,123,0,0.4);
}
.btn-orange:hover { transform: translateY(-2px); }
.btn-outline {
  padding: 12px 28px;
  border: 2px solid rgba(255,209,102,0.4);
  color: #ffd166;
  border-radius: 50px;
  font-family: 'Nunito', sans-serif;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.2s;
}
.btn-outline:hover { border-color: #ffd166; background: rgba(255,209,102,0.05); }

@media (max-width: 768px) {
  .about-hero { grid-template-columns: 1fr; padding: 100px 24px 60px; text-align: center; }
  .about-hero-visual { display: none; }
  .story-grid { grid-template-columns: 1fr; }
  .timeline::before { left: 20px; }
  .timeline-item, .timeline-item.right { padding: 0 0 0 60px; justify-content: flex-start; }
  .timeline-dot { left: 20px; }
}
</style>