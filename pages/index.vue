<script setup>
definePageMeta({
  layout: false,
})

const recommendation = ref('')

const scrollToSection = (id) => {
  window.location.hash = id
}

const recommend = (type) => {
  if (type === 'daily') recommendation.value = 'Recommended: Daily Attar – Light, refined and subtle.'
  if (type === 'special') recommendation.value = 'Recommended: Premium Oud – Deep, bold and commanding.'
  if (type === 'work') recommendation.value = 'Recommended: Fresh Musk Blend – Professional and clean.'
}
</script>

<template>
  <div class="alimaam-site">
    <header>
      <div class="logo">AL-IMAAM</div>
      <nav>
        <a href="#">Home</a>
        <a href="#sunnah">Sunnah</a>
        <a href="#gifts">Gifts</a>
        <a href="#quiz">Quiz</a>
        <a href="#about">About</a>
      </nav>
    </header>

    <section class="hero">
      <div>
        <h1>The Scent of Leadership.</h1>
        <p>Pure, alcohol-free Attars and artisanal French perfumes crafted for the modern connoisseur.</p>
        <button type="button" @click="scrollToSection('sunnah')">Explore Collection</button>
      </div>
    </section>

    <div class="trust">
      <div>✔ 100% Alcohol-Free</div>
      <div>✔ Sourced from Grasse</div>
      <div>✔ Long Lasting (12+ Hours)</div>
    </div>

    <section id="sunnah" class="section">
      <h2>The Sunnah Collection</h2>
      <div class="split">
        <img src="/images/hero.jpg" alt="Sunnah collection perfume bottles" >
        <div class="split-text">
          <p>Traditional non-alcoholic concentrated oils crafted in reverence to timeless tradition.</p>
          <div class="products">
            <div class="card">
              <h3>Royal Oud Attar</h3>
              <p class="price">₹2,499</p>
              <div class="notes">
                <div><strong>Top:</strong> <span>Oud</span><span>Spice</span></div>
                <div><strong>Heart:</strong> <span>Amber</span><span>Rose</span></div>
                <div><strong>Base:</strong> <span>Musk</span></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section">
      <h2>Imaam's Choice</h2>
      <div class="bundle-box">
        <div class="card">
          <h3>Daily Attar</h3>
          <p class="price">₹1,499</p>
        </div>
        <div class="card">
          <h3>Premium Oud</h3>
          <p class="price">₹3,999</p>
        </div>
      </div>
      <div class="bundle-summary">
        <p><strong>Bundle Price: ₹4,999</strong></p>
        <button type="button" @click="window.open('https://wa.me/917004688757')">Enquire via WhatsApp</button>
      </div>
    </section>

    <section id="gifts" class="section">
      <h2>The Gift of AL-IMAAM</h2>
      <div class="split">
        <img src="/images/person-2.jpg" alt="AL-IMAAM gift set" >
        <div class="split-text">
          <p>Velvet-lined luxury boxes with customizable message cards. A gift worthy of distinction.</p>
          <button type="button" @click="window.open('https://wa.me/917004688757')">Request a Gift Box</button>
        </div>
      </div>
    </section>

    <section id="quiz" class="section">
      <h2>Find Your Signature</h2>
      <div class="quiz">
        <p>Choose your preference:</p>
        <button type="button" @click="recommend('daily')">Daily</button>
        <button type="button" @click="recommend('special')">Special Occasion</button>
        <button type="button" @click="recommend('work')">Work</button>
        <div id="result">{{ recommendation }}</div>
      </div>
    </section>

    <section id="about" class="section">
      <h2>About AL-IMAAM</h2>
      <p class="about-copy">
        AL-IMAAM stands as a bridge between ancient devotion and modern refinement.
        Each fragrance is a declaration of identity — direct, yet poetic.
        "Experience the timeless essence of purity."
      </p>
    </section>

    <footer>
      <p>Email: alimamluxury55@gmail.com</p>
      <p>WhatsApp: +91 70046 88757</p>
      <p>© 2026 AL-IMAAM. All Rights Reserved.</p>
    </footer>

    <a class="whatsapp" href="https://wa.me/917004688757" target="_blank" rel="noopener">💬</a>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=Montserrat:wght@300;400;500&display=swap');

* { margin: 0; padding: 0; box-sizing: border-box; }
.alimaam-site { font-family: Montserrat, sans-serif; background: #0f0f0f; color: #fff; }
h1, h2, h3 { font-family: 'Playfair Display', serif; }
a { text-decoration: none; color: inherit; }

header {
  display: flex; justify-content: space-between; align-items: center;
  padding: 20px 60px; background: #0f0f0f; position: sticky; top: 0; z-index: 1000;
}
.logo { font-size: 28px; letter-spacing: 3px; color: #d4af37; }
nav a { margin-left: 25px; font-size: 14px; transition: .3s; }
nav a:hover { color: #d4af37; }

.hero {
  min-height: 95vh;
  background: linear-gradient(rgba(0, 0, 0, .6), rgba(0, 0, 0, .7)),
    url('/images/hero.jpg') center/cover no-repeat;
  display: flex; justify-content: center; align-items: center; text-align: center; padding: 20px;
}
.hero h1 { font-size: clamp(2.2rem, 6vw, 60px); color: #d4af37; }
.hero p { margin-top: 15px; font-size: 18px; letter-spacing: 1px; max-width: 740px; }
.hero button {
  margin-top: 25px; padding: 12px 30px; border: none; background: #d4af37; color: #000;
  font-weight: 500; cursor: pointer; transition: .3s;
}
.hero button:hover { background: #fff; }

.trust {
  background: #111; padding: 20px; text-align: center; display: flex;
  justify-content: center; gap: 60px; flex-wrap: wrap;
}
.trust div { color: #d4af37; font-weight: 500; }

.section { padding: 80px 60px; }
.section h2 { text-align: center; margin-bottom: 40px; color: #d4af37; }
.products { display: flex; gap: 30px; flex-wrap: wrap; justify-content: center; margin-top: 16px; }

.card {
  background: #1a1a1a; padding: 20px; width: 280px; border-radius: 10px;
  transition: .3s;
}
.card:hover { transform: translateY(-8px); }
.price { color: #d4af37; margin: 8px 0; }

.notes { margin-top: 10px; font-size: 13px; }
.notes div { margin: 4px 0; }
.notes span { background: #222; padding: 4px 8px; border-radius: 5px; margin: 2px; display: inline-block; }

.split { display: flex; gap: 40px; align-items: center; flex-wrap: wrap; justify-content: center; }
.split img { width: 100%; max-width: 500px; border-radius: 10px; max-height: 420px; object-fit: cover; }
.split-text { flex: 1; min-width: min(100%, 320px); }

.bundle-box { display: flex; gap: 30px; justify-content: center; flex-wrap: wrap; }
.bundle-summary { text-align: center; margin-top: 20px; }
.bundle-summary button,
.split-text button,
.quiz button {
  margin-top: 10px; padding: 12px 30px; background: #d4af37; border: none; color: #000; cursor: pointer;
}

.quiz { max-width: 600px; margin: auto; text-align: center; }
.quiz button { margin: 10px; padding: 8px 20px; }
#result { margin-top: 20px; font-weight: 500; }

.about-copy { max-width: 800px; margin: auto; text-align: center; line-height: 1.8; }

footer { background: #000; padding: 40px; text-align: center; color: #aaa; font-size: 14px; }

.whatsapp {
  position: fixed; bottom: 20px; right: 20px;
  background: #25D366; color: #fff; padding: 15px 18px;
  border-radius: 50%; font-size: 22px;
  box-shadow: 0 0 15px rgba(0, 0, 0, .5);
}

@media (max-width: 700px) {
  header { padding: 16px; flex-direction: column; gap: 12px; }
  nav { display: flex; gap: 12px; flex-wrap: wrap; justify-content: center; }
  nav a { margin: 0; }
  .section { padding: 60px 20px; }
}
</style>
