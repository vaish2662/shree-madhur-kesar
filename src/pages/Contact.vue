<template>
  <div class="contact-page">
    <!-- Header -->
    <div class="contact-header">
      <div class="ch-blob chb1"></div>
      <div class="ch-blob chb2"></div>
      <div class="ch-content">
        <div class="section-tag">Get In Touch</div>
        <h1 class="contact-title">We'd love to<br><span class="accent">hear from you</span></h1>
        <p class="contact-subtitle">Questions about orders, bulk pricing, or just want to say hi — we're always happy to chat on WhatsApp or email!</p>
      </div>
    </div>

    <!-- Contact Cards -->
    <section class="contact-section">
      <div class="container">
        <div class="contact-grid">
          <!-- Contact Info -->
          <div class="info-col">
            <h2 class="info-title">Contact Details</h2>
            <div class="info-cards">

              <!-- WhatsApp -->
              <a href="https://wa.me/91XXXXXXXXXX" target="_blank" class="info-card whatsapp-card">
                <div class="info-icon">
                  <svg width="26" height="26" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.123.554 4.118 1.528 5.855L.057 23.882l6.18-1.622A11.94 11.94 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.894a9.87 9.87 0 01-5.031-1.378l-.36-.214-3.733.979.998-3.648-.235-.374A9.862 9.862 0 012.106 12C2.106 6.579 6.579 2.106 12 2.106c5.42 0 9.894 4.473 9.894 9.894 0 5.42-4.474 9.894-9.894 9.894z"/></svg>
                </div>
                <div>
                  <div class="info-label">WhatsApp (Fastest)</div>
                  <div class="info-value">+91 XXXXX XXXXX</div>
                </div>
                <div class="info-arrow">→</div>
              </a>

              <!-- Email -->
              <a href="mailto:YOUR_EMAIL@gmail.com" class="info-card email-card">
                <div class="info-icon email-icon">
                  <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
                </div>
                <div>
                  <div class="info-label">Email Us</div>
                  <div class="info-value">shreemadhurkesarmango@gmail.com</div>
                </div>
                <div class="info-arrow email-arrow">→</div>
              </a>

              <!-- Location -->
              <div class="info-card">
                <div class="info-icon loc-icon">📍</div>
                <div>
                  <div class="info-label">Location</div>
                  <div class="info-value">Nanded, Maharashtra, India</div>
                  <div class="info-sub">Also delivering to Pune, Hyderabad & all Maharashtra</div>
                </div>
              </div>

              <!-- Response Time -->
              <div class="info-card">
                <div class="info-icon time-icon">🕐</div>
                <div>
                  <div class="info-label">Response Time</div>
                  <div class="info-value">2–4 hrs on WhatsApp · 24 hrs on Email</div>
                </div>
              </div>

              <!-- Delivery -->
              <div class="info-card">
                <div class="info-icon delivery-icon">🚚</div>
                <div>
                  <div class="info-label">Delivery Areas</div>
                  <div class="info-value">All across Maharashtra</div>
                  <div class="info-sub">Primarily Nanded · Pune · Hyderabad</div>
                </div>
              </div>

            </div>
          </div>

          <!-- Quick Order -->
          <div class="order-col">
            <h2 class="info-title">Quick Order via WhatsApp</h2>
            <p class="order-intro">Choose what you're interested in and we'll open WhatsApp with a pre-filled message for you.</p>
            <div class="quick-btns">
              <a
                v-for="item in quickOrders"
                :key="item.label"
                :href="item.link"
                target="_blank"
                class="quick-btn"
              >
                <span class="qb-icon">{{ item.icon }}</span>
                <span class="qb-label">{{ item.label }}</span>
                <span class="qb-arrow">→</span>
              </a>
            </div>

            <div class="season-note">
              <span class="season-icon">📅</span>
              <div>
                <strong>Mango Season:</strong> May – July<br>
                <span>Pre-book your order early to avoid disappointment!</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
const quickOrders = [
  { icon: '🥭', label: 'Order Fresh Kesar Mangoes', link: "https://wa.me/91XXXXXXXXXX?text=Hello! I'd like to order fresh Kesar mangoes. Please share availability and pricing." },
  { icon: '🍬', label: 'Order Mango Candy (Aam Papad)', link: "https://wa.me/91XXXXXXXXXX?text=Hello! I'm interested in Aam Papad (mango candy). Please share details." },
  { icon: '🌟', label: 'Order Dried Mango Slices', link: "https://wa.me/91XXXXXXXXXX?text=Hello! I'd like to order dried mango slices. Please share availability." },
  { icon: '📦', label: 'Bulk / Corporate Order', link: "https://wa.me/91XXXXXXXXXX?text=Hello! I'm interested in placing a bulk order for mangoes. Please share pricing details." },
  { icon: '🎁', label: 'Mango Gift Box Enquiry', link: "https://wa.me/91XXXXXXXXXX?text=Hello! I'm interested in the Kesar Mango Gift Box. Please share details and pricing." },
];
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&family=Nunito:wght@400;600;700&display=swap');

.contact-page { background: #fdf6ec; }

/* HEADER */
.contact-header {
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #fff8ee, #ffe8b3);
  padding: 120px 64px 80px;
  text-align: center;
}
.ch-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(50px);
  opacity: 0.45;
}
.chb1 { width: 300px; height: 300px; background: #ffd166; top: -80px; right: 10%; }
.chb2 { width: 200px; height: 200px; background: #ff9f43; bottom: -60px; left: 20%; }
.ch-content { position: relative; z-index: 1; }
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
.contact-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2rem, 5vw, 3.2rem);
  color: #1a0a00;
  margin: 0 0 16px;
  line-height: 1.2;
}
.accent { color: #e07b00; font-style: italic; }
.contact-subtitle {
  font-family: 'Nunito', sans-serif;
  color: #5a3a1a;
  font-size: 1.05rem;
  max-width: 520px;
  margin: 0 auto;
  line-height: 1.6;
}

/* CONTACT SECTION */
.contact-section { padding: 80px 0 100px; }
.container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 64px;
  align-items: start;
}
.info-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  color: #1a0a00;
  margin: 0 0 24px;
}
.info-cards { display: flex; flex-direction: column; gap: 14px; }
.info-card {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 18px 20px;
  border-radius: 16px;
  background: #fff;
  border: 1px solid rgba(180,90,0,0.1);
  text-decoration: none;
  color: inherit;
  transition: all 0.2s;
}
.info-card:hover { box-shadow: 0 6px 24px rgba(180,90,0,0.1); transform: translateY(-2px); }

/* WhatsApp card */
.whatsapp-card { border-color: rgba(37,211,102,0.3); background: linear-gradient(135deg, #f0fff6, #e8fdf0); }
.whatsapp-card:hover { box-shadow: 0 6px 24px rgba(37,211,102,0.2); border-color: #25D366; }

/* Email card */
.email-card { border-color: rgba(66,133,244,0.25); background: linear-gradient(135deg, #f0f4ff, #e8eeff); }
.email-card:hover { box-shadow: 0 6px 24px rgba(66,133,244,0.15); border-color: #4285f4; }

.info-icon {
  width: 48px; height: 48px;
  border-radius: 12px;
  background: linear-gradient(135deg, #25D366, #128C7E);
  color: white;
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
}
.email-icon { background: linear-gradient(135deg, #4285f4, #1a73e8); }
.loc-icon  { background: linear-gradient(135deg, #e07b00, #c45e00); font-size: 1.4rem; }
.time-icon { background: linear-gradient(135deg, #fff3d6, #ffd166); font-size: 1.4rem; }
.delivery-icon { background: linear-gradient(135deg, #fde8ff, #d166ff); font-size: 1.4rem; }

.info-label {
  font-family: 'Nunito', sans-serif;
  font-size: 0.72rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #7a5030;
  margin-bottom: 3px;
}
.info-value {
  font-family: 'Nunito', sans-serif;
  font-size: 0.95rem;
  font-weight: 600;
  color: #1a0a00;
}
.info-sub {
  font-family: 'Nunito', sans-serif;
  font-size: 0.78rem;
  color: #9a6040;
  margin-top: 2px;
}
.info-arrow { margin-left: auto; color: #25D366; font-size: 1.1rem; font-weight: 700; }
.email-arrow { color: #4285f4; }

/* QUICK ORDER */
.order-intro {
  font-family: 'Nunito', sans-serif;
  color: #7a5030;
  font-size: 0.95rem;
  margin: 0 0 24px;
  line-height: 1.6;
}
.quick-btns { display: flex; flex-direction: column; gap: 12px; margin-bottom: 28px; }
.quick-btn {
  display: flex;
  align-items: center;
  gap: 14px;
  padding: 15px 20px;
  border-radius: 14px;
  background: linear-gradient(135deg, #25D366, #128C7E);
  color: white;
  text-decoration: none;
  transition: all 0.2s;
  box-shadow: 0 4px 16px rgba(37,211,102,0.2);
}
.quick-btn:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(37,211,102,0.35); }
.qb-icon { font-size: 1.3rem; }
.qb-label { font-family: 'Nunito', sans-serif; font-weight: 700; font-size: 0.95rem; flex: 1; }
.qb-arrow { opacity: 0.7; }

.season-note {
  display: flex;
  gap: 14px;
  align-items: flex-start;
  padding: 20px;
  border-radius: 14px;
  background: linear-gradient(135deg, #fff8ee, #fff3d6);
  border: 1px solid rgba(180,90,0,0.15);
}
.season-icon { font-size: 1.5rem; flex-shrink: 0; }
.season-note div {
  font-family: 'Nunito', sans-serif;
  font-size: 0.9rem;
  color: #5a3a1a;
  line-height: 1.6;
}
.season-note strong { color: #b45a00; }

@media (max-width: 768px) {
  .contact-header { padding: 100px 24px 60px; }
  .contact-grid { grid-template-columns: 1fr; gap: 48px; }
}
</style>