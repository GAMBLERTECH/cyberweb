# cyberweb

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MASTERS Cyber & Perfume Refill</title>

<style>
:root {
  --navy: #101a3b;
  --blue: #4473ff;
  --gold: #f4c96d;
  --light: #f5f7ff;
  --text: #22304c;
  --muted: #667498;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
  scroll-padding-top: 85px;
}

body {
  font-family: Arial, sans-serif;
  color: var(--text);
  line-height: 1.7;
  background:
    radial-gradient(circle at top left, rgba(124, 154, 255, 0.18), transparent 28%),
    radial-gradient(circle at bottom right, rgba(244, 201, 109, 0.14), transparent 32%),
    linear-gradient(180deg, #fbfcff 0%, #f4f7ff 100%);
}

a {
  text-decoration: none;
  color: inherit;
}

header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 17px 7%;
  background: linear-gradient(135deg, rgba(255,255,255,0.96), rgba(245,247,255,0.96));
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 10px 30px rgba(15, 28, 58, 0.08);
  border-bottom: 1px solid rgba(160, 180, 255, 0.35);
}

.logo {
  color: var(--navy);
  font-size: 20px;
  font-weight: 900;
  line-height: 1.2;
}

.logo span {
  color: var(--blue);
}

.logo small {
  display: block;
  font-size: 10px;
  letter-spacing: 2px;
  margin-top: 5px;
}

nav {
  display: flex;
  align-items: center;
  gap: 25px;
}

nav a {
  font-size: 13px;
  font-weight: bold;
}

nav a:hover {
  color: var(--blue);
}

.menu-toggle {
  display: none;
  border: 0;
  background: none;
  font-size: 25px;
  cursor: pointer;
  color: var(--navy);
}

.hero {
  min-height: 570px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  gap: 35px;
  padding: 70px 8%;
  background:
    radial-gradient(circle at 82% 18%, #cbd7ff, transparent 35%),
    radial-gradient(circle at 15% 90%, #fff0d1, transparent 30%),
    linear-gradient(135deg, #f9faff, var(--light));
}

.tagline {
  color: var(--blue);
  font-size: 11px;
  font-weight: bold;
  letter-spacing: 2px;
  margin-bottom: 15px;
}

.hero h1 {
  color: var(--navy);
  font-size: clamp(40px, 5vw, 63px);
  line-height: 1.13;
  letter-spacing: -2px;
  margin-bottom: 20px;
}

.hero h1 span,
.perfume-content h2 span {
  color: var(--blue);
}

.hero-content > p:not(.tagline) {
  max-width: 480px;
  color: var(--muted);
  margin-bottom: 28px;
}

.hero-buttons {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.btn {
  display: inline-block;
  border: 0;
  border-radius: 12px;
  padding: 13px 20px;
  background: linear-gradient(135deg, #5a84ff 0%, #2e5af0 50%, #2044d9 100%);
  color: white;
  font-size: 12px;
  font-weight: bold;
  cursor: pointer;
  transition: 0.25s ease;
  box-shadow: 0 10px 25px rgba(68, 115, 255, 0.28), inset 0 1px 0 rgba(255,255,255,0.4);
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 16px 32px rgba(68, 115, 255, 0.35), inset 0 1px 0 rgba(255,255,255,0.5);
}

.btn-outline {
  background: white;
  border: 1px solid #dce1ef;
  color: var(--navy);
}

.hero-image {
  display: grid;
  place-items: center;
}

.image-card {
  width: min(100%, 440px);
  min-height: 320px;
  padding: 35px 20px;
  border-radius: 30px;
  text-align: center;
  background: linear-gradient(145deg, rgba(255,255,255,0.98), rgba(236,241,255,0.98), rgba(255,248,234,0.98));
  box-shadow: 0 30px 80px rgba(20, 32, 71, 0.17), 0 0 40px rgba(122, 146, 255, 0.18);
  border: 1px solid rgba(255,255,255,0.9);
}

.laptop {
  font-size: 115px;
  filter: drop-shadow(0 12px 18px rgba(68, 115, 255, 0.18));
}

.perfume-bottle {
  position: relative;
  width: 96px;
  height: 140px;
  margin: -8px auto 0;
  display: flex;
  align-items: center;
  justify-content: center;
  filter: drop-shadow(0 16px 24px rgba(214, 160, 66, 0.28));
}

.perfume-cap {
  position: absolute;
  top: -18px;
  width: 42px;
  height: 24px;
  border-radius: 8px 8px 4px 4px;
  background: linear-gradient(180deg, #f7df9a, #c78d32);
  box-shadow: inset 0 2px 6px rgba(255,255,255,0.8);
}

.perfume-cap::before {
  content: "";
  position: absolute;
  inset: 4px 7px 6px;
  border-radius: 4px;
  background: linear-gradient(180deg, rgba(255,255,255,0.9), rgba(255,255,255,0.15));
}

.perfume-glass {
  position: absolute;
  bottom: 0;
  width: 96px;
  height: 126px;
  border-radius: 18px 18px 26px 26px;
  background: linear-gradient(180deg,
    rgba(255, 255, 255, 0.95) 0%,
    rgba(255, 239, 202, 0.88) 12%,
    rgba(215, 173, 87, 0.82) 42%,
    rgba(145, 95, 36, 0.86) 100%
  );
  border: 2px solid rgba(255,255,255,0.9);
  box-shadow: inset 0 0 12px rgba(255,255,255,0.8), inset 12px 0 18px rgba(255,255,255,0.45), inset -12px 0 18px rgba(109, 68, 16, 0.18);
  overflow: hidden;
}

.perfume-glass::before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(120deg, rgba(226, 91, 91, 0.73)), rgba(255,255,255,0.08) 28%, transparent 50%, rgba(255,255,255,0.2));
  transform: skewX(-18deg);
}

.perfume-glass::after {
  content: "";
  position: absolute;
  inset: 14px 24px 18px 24px;
  border-radius: 12px;
  border: 1px solid rgba(255,255,255,0.75);
  background: rgba(255,255,255,0.12);
}

.image-card h3 {
  margin-top: 10px;
  color: var(--navy);
}

.image-card p {
  color: var(--muted);
  font-size: 13px;
}

.section {
  padding: 80px 7%;
}

.section-heading {
  text-align: center;
  margin-bottom: 40px;
}

.section-heading h2 {
  font-size: clamp(29px, 4vw, 40px);
  color: var(--navy);
  line-height: 1.2;
}

.section-heading > p:last-child {
  color: var(--muted);
  font-size: 13px;
  margin-top: 12px;
}

.cards {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 20px;
}

.card {
  padding: 25px 20px;
  border: 1px solid rgba(206, 216, 255, 0.9);
  border-radius: 18px;
  transition: 0.25s;
  background: linear-gradient(180deg, rgba(255,255,255,0.98), rgba(245,247,255,0.96));
  box-shadow: 0 10px 25px rgba(18, 34, 77, 0.04);
}

.card:hover {
  transform: translateY(-6px);
  box-shadow: 0 18px 40px rgba(63, 92, 207, 0.12);
  border-color: #b6c7ff;
}

.card-icon {
  width: 53px;
  height: 53px;
  display: grid;
  place-items: center;
  border-radius: 14px;
  background: linear-gradient(145deg, #edf1ff, #dde8ff);
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.9), 0 8px 18px rgba(68, 115, 255, 0.12);
  font-size: 25px;
  margin-bottom: 18px;
}

.card h3 {
  font-size: 16px;
  color: var(--navy);
  margin-bottom: 10px;
}

.card p {
  font-size: 12px;
  color: var(--muted);
  margin-bottom: 20px;
}

.service-link {
  color: var(--blue);
  font-weight: bold;
  font-size: 11px;
}

.perfume-section {
  background:
    radial-gradient(circle at 80% 48%, #344b86 0, transparent 36%),
    linear-gradient(125deg, #101a3c, #1b2d60 65%, #25396e);
  color: white;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  align-items: center;
  padding: 80px 8%;
}

.perfume-content h2 {
  font-size: clamp(38px, 5vw, 55px);
  line-height: 1.15;
  margin-bottom: 20px;
}

.perfume-content h2 span {
  color: var(--gold);
}

.perfume-content > p:not(.tagline) {
  color: #bdc7de;
  font-size: 13px;
}

.fragrance-options {
  display: grid;
  gap: 17px;
  margin: 30px 0;
}

.fragrance-options > div {
  display: flex;
  align-items: center;
  gap: 15px;
}

.fragrance-options > div > span {
  width: 38px;
  height: 38px;
  display: grid;
  place-items: center;
  border: 1px solid #ffffff30;
  border-radius: 10px;
  color: var(--gold);
  font-size: 20px;
}

.fragrance-options h3 {
  font-size: 13px;
}

.fragrance-options p {
  color: #bdc7de;
  font-size: 11px;
}

.perfume-content .btn {
  background: linear-gradient(135deg, #ffdc86, #e9b84c);
  color: var(--navy);
  box-shadow: 0 8px 22px #f0c66b30;
}

.bottle-display {
  min-height: 340px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  position: relative;
  padding-bottom: 35px;
}

.bottle {
  height: 155px;
  width: 80px;
  border-radius: 12px 12px 18px 18px;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  font-size: 10px;
  font-weight: bold;
  letter-spacing: 1px;
  color: #593f20;
  background: linear-gradient(100deg, #ae8146, #f0d9a5, #a47b41);
  border: 1px solid #dfc18b;
  box-shadow: inset 5px 0 12px #ffffff50,
              0 20px 25px #00000030;
  position: relative;
}

.bottle::before {
  content: "";
  position: absolute;
  width: 28px;
  height: 27px;
  background: linear-gradient(90deg, #8e6c3c, #f2d7a0, #8e6c3c);
  top: -27px;
  border-radius: 4px 4px 0 0;
}

.bottle-one {
  transform: rotate(-8deg) scale(.85);
}

.bottle-two {
  height: 180px;
  background: linear-gradient(100deg, #aebbd0, #f8fbff, #9ba9c0);
  z-index: 2;
}

.bottle-two::before {
  background: linear-gradient(90deg, #9da9ba, white, #9da9ba);
}

.bottle-three {
  transform: rotate(8deg) scale(.9);
  background: linear-gradient(100deg, #34271e, #8b6846, #29201a);
  color: #f4d8a5;
}

.bottle-display > p {
  position: absolute;
  bottom: 5px;
  color: #b9c3dc;
  font-size: 9px;
  letter-spacing: 3px;
}

.why-us {
  background: linear-gradient(135deg, #f3f6ff, #fffaf0);
}

.benefits {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 25px;
  margin-top: 35px;
  text-align: center;
}

.benefits > div {
  padding: 25px 15px;
  background: white;
  border-radius: 15px;
}

.benefits span {
  display: inline-grid;
  place-items: center;
  width: 40px;
  height: 40px;
  background: #e4f7ed;
  color: #248b61;
  border-radius: 50%;
  font-size: 21px;
}

.benefits h3 {
  font-size: 15px;
  margin: 13px 0 7px;
}

.benefits p {
  color: var(--muted);
  font-size: 12px;
}

.contact-section {
  padding: 80px 8%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 55px;
  background:
    radial-gradient(circle at 10% 10%, #344b86 0, transparent 36%),
    linear-gradient(125deg, #101a3c, #1b2d60 65%, #25396e);
  color: white;
}

.contact-info h2 {
  font-size: clamp(30px, 4vw, 42px);
  line-height: 1.2;
  margin-bottom: 20px;
}

.contact-info > p:not(.tagline) {
  color: #c4cee4;
  font-size: 13px;
  margin: 17px 0;
}

.contact-info small {
  display: block;
  margin-top: 30px;
  color: #a9b6d3;
  font-size: 11px;
}

.contact-form {
  background: linear-gradient(145deg, #ffffff, #f7f8ff);
  color: var(--text);
  padding: 28px;
  border-radius: 18px;
  box-shadow: 0 20px 55px #080f281f, 0 0 25px #829cff20;
  border: 1px solid #ffffff;
}

.contact-form h3 {
  font-size: 21px;
  margin-bottom: 20px;
  color: var(--navy);
}

.contact-form label {
  display: block;
  font-size: 12px;
  font-weight: bold;
  margin: 14px 0 6px;
}

.contact-form input,
.contact-form select,
.contact-form textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #dfe4ef;
  border-radius: 8px;
  background: #fbfcff;
  font: inherit;
  font-size: 12px;
  outline: none;
}

.contact-form input:focus,
.contact-form select:focus,
.contact-form textarea:focus {
  border-color: var(--blue);
  box-shadow: 0 0 0 3px #315cf515;
}

.contact-form textarea {
  resize: vertical;
}

.contact-form button {
  width: 100%;
  margin-top: 18px;
}

#formMessage {
  font-size: 12px;
  color: #b43d3d;
  margin-top: 10px;
}

footer {
  text-align: center;
  padding: 30px 15px;
  background: linear-gradient(110deg, #0b142b, #18264d);
  color: #aeb9d1;
  font-size: 11px;
}

.footer-logo {
  display: inline-block;
  font-weight: 900;
  font-size: 18px;
  color: white;
  margin-bottom: 8px;
}

footer p {
  margin-top: 5px;
}

@media (max-width: 900px) {
  .cards {
    grid-template-columns: repeat(2, 1fr);
  }

  .hero {
    padding-inline: 6%;
  }

  .contact-section {
    gap: 30px;
    padding-inline: 6%;
  }
}

@media (max-width: 650px) {
  header {
    padding: 15px 5%;
  }

  .menu-toggle {
    display: block;
  }

  nav {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    flex-direction: column;
    align-items: stretch;
    gap: 0;
    background: white;
    padding: 10px 6% 20px;
    box-shadow: 0 12px 20px #101c3b14;
  }

  nav.open {
    display: flex;
  }

  nav a {
    padding: 12px 0;
  }

  .hero,
  .perfume-section,
  .contact-section {
    grid-template-columns: 1fr;
  }

  .hero {
    padding: 50px 6%;
    gap: 30px;
  }

  .hero h1 {
    font-size: 44px;
  }

  .image-card {
    min-height: 270px;
  }

  .laptop {
    font-size: 95px;
  }

  .perfume-emoji {
    font-size: 60px;
  }

  .section {
    padding: 60px 6%;
  }

  .cards {
    grid-template-columns: 1fr;
  }

  .perfume-section {
    padding: 60px 6%;
    gap: 35px;
  }

  .bottle-display {
    min-height: 280px;
    gap: 8px;
  }

  .bottle {
    width: 65px;
  }

  .benefits {
    grid-template-columns: 1fr;
    gap: 13px;
  }

  .contact-section {
    padding: 60px 6%;
  }

  .contact-form {
    padding: 22px 17px;
  }
}

@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }

  *, *::before, *::after {
    transition: none !important;
  }
}
</style>
</head>

<body>

<header>
  <a href="#home" class="logo">
    MASTERS <span>CYBER</span>
    <small>& PERFUME REFILL</small>
  </a>

  <button class="menu-toggle" id="menuToggle"
          aria-label="Toggle navigation"
          aria-expanded="false">☰</button>

  <nav id="navigation">
    <a href="#home">Home</a>
    <a href="#services">Cyber Services</a>
    <a href="#perfumes">Perfume Refill</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section class="hero" id="home">
  <div class="hero-content">
    <p class="tagline">YOUR TRUSTED SERVICE CENTRE</p>
    <h1>Smart Services.<br><span>Beautiful Scents.</span></h1>
    <p>
      Your one-stop destination for cyber services, document
      printing, online applications and quality perfume refills.
    </p>

    <div class="hero-buttons">
      <a href="#services" class="btn">Explore Services</a>
      <a href="#contact" class="btn btn-outline">Contact Us</a>
    </div>
  </div>

  <div class="hero-image">
    <div class="image-card">
      <div class="laptop">💻</div>
      <div class="perfume-bottle" aria-label="Shiny perfume bottle">
        <div class="perfume-cap"></div>
        <div class="perfume-glass"></div>
      </div>
      <h3>Here Convenience Meets Style </h3>
      <p>Professional service, every time.</p>
    </div>
  </div>
</section>

<section class="section" id="services">
  <div class="section-heading">
    <p class="tagline">WHAT WE OFFER</p>
    <h2>Our Cyber Services</h2>
    <p>Reliable assistance for your everyday digital needs.</p>
  </div>

  <div class="cards">
    <article class="card">
      <div class="card-icon">🖨️</div>
      <h3>Printing & Photocopying</h3>
      <p>Black-and-white and colour printing, photocopies and document editing.</p>
      <a href="#contact" class="service-link"
         data-service="Printing and photocopying">Enquire now →</a>
    </article>

    <article class="card">
      <div class="card-icon">🌐</div>
      <h3>Online services</h3>
      <p>Assistance with online forms, digital submissions and other online services.</p>
      <a href="#contact" class="service-link"
         data-service="Online applications">Enquire now →</a>
    </article>

    <article class="card">
      <div class="card-icon">📝</div>
      <h3>Typing & Scanning</h3>
      <p>Typing, document scanning, CV formatting propasals editing,bulk printing.</p>
      <a href="#contact" class="service-link"
         data-service="Typing and scanning">Enquire now →</a>
    </article>

    <article class="card">
      <div class="card-icon">🎨</div>
      <h3>Design & Binding</h3>
      <p>Posters, business designs, document binding and lamination.</p>
      <a href="#contact" class="service-link"
         data-service="Design and binding">Enquire now →</a>
    </article>
  </div>
</section>

<section class="perfume-section" id="perfumes">
  <div class="perfume-content">
    <p class="tagline" style="color:var(--gold)">
      DISCOVER YOUR SIGNATURE SCENT
    </p>
    <h2>Fragrance That<br><span>Defines You.</span></h2>
    <p>
      Explore fragrance refills for different moods, personalities
      and occasions. Ask about available scents and bottle sizes.
    </p>

    <div class="fragrance-options">
      <div>
        <span>✦</span>
        <div>
          <h3>For Men</h3>
          <p>Fresh, woody and bold scents.</p>
        </div>
      </div>

      <div>
        <span>✧</span>
        <div>
          <h3>For Women</h3>
          <p>Floral, warm and elegant scents.</p>
        </div>
      </div>

      <div>
        <span>◇</span>
        <div>
          <h3>Unisex</h3>
          <p>Versatile scents for everyone.</p>
        </div>
      </div>
    </div>

    <a href="#contact" class="btn" data-service="Perfume refill">
      Enquire About Perfumes
    </a>
  </div>

  <div class="bottle-display">
    <div class="bottle bottle-one"><span>NO. 01<br>AMBER</span></div>
    <div class="bottle bottle-two"><span>NO. 02<br>PURE</span></div>
    <div class="bottle bottle-three"><span>NO. 03<br>OUD</span></div>
    <p>THE FRAGRANCE COLLECTION</p>
  </div>
</section>

<section class="section why-us">
  <div class="section-heading">
    <p class="tagline">WHY CHOOSE US?</p>
    <h2>Service You Can Trust</h2>
  </div>

  <div class="benefits">
    <div>
      <span>✓</span>
      <h3>Friendly Assistance</h3>
      <p>Helpful service for every client.</p>
    </div>

    <div>
      <span>✓</span>
      <h3>Clear Pricing</h3>
      <p>Confirm prices before work begins.</p>
    </div>

    <div>
      <span>✓</span>
      <h3>Convenience</h3>
      <p>Cyber services and fragrance refills in one place.</p>
    </div>
  </div>
</section>

<section class="contact-section" id="contact">
  <div class="contact-info">
    <p class="tagline" style="color:var(--gold)">GET IN TOUCH</p>
    <h2>How Can We Help You?</h2>
    <p>Send an enquiry and continue the conversation on WhatsApp.</p>
    <p>located at owour church junction</p>
    <p>📲 0769535087</p>
    <p>⏰ opened 7 AM to 8 PM</p>
    
  </div>

  <form class="contact-form" id="contactForm">
    <h3>Send an Enquiry</h3>

    <label for="name">Your Name</label>
    <input type="text" id="name" placeholder="Enter your name" required>

    <label for="phone">Phone Number (optional)</label>
    <input type="tel" id="phone" placeholder="07XX XXX XXX">

    <label for="service">Select a Service</label>
    <select id="service" required>
      <option value="">Choose a service</option>
      <option>Printing and photocopying</option>
      <option>Online services</option>
      <option>Typing and scanning</option>
      <option>Design and binding</option>
      <option>Perfume refill</option>
      <option>Other enquiry</option>
    </select>

    <label for="message">Your Message</label>
    <textarea id="message" rows="4"
      placeholder="Tell us what you need..." required></textarea>

    <button type="submit" class="btn">Send via WhatsApp ↗</button>
    <p id="formMessage" role="status"></p>
  </form>
</section>

<footer>
  <a href="#home" class="footer-logo">MASTERS CYBER</a>
  <p>Cyber Services & Perfume Refill</p>
  <p>© <span id="year"></span> Masters cyber and perfume refill. All rights reserved.</p>
</footer>

<script>
// Your business WhatsApp number.
// Kenyan format: 2547XXXXXXXX, digits only.
const BUSINESS_WHATSAPP = "254769535087";
const BUSINESS_DISPLAY_NUMBER = "0769535087";

// Mobile navigation
const menuToggle = document.getElementById("menuToggle");
const navigation = document.getElementById("navigation");

menuToggle.addEventListener("click", () => {
  const isOpen = navigation.classList.toggle("open");
  menuToggle.setAttribute("aria-expanded", String(isOpen));
});

navigation.querySelectorAll("a").forEach(link => {
  link.addEventListener("click", () => {
    navigation.classList.remove("open");
    menuToggle.setAttribute("aria-expanded", "false");
  });
});

// Automatically update the copyright year
document.getElementById("year").textContent =
  new Date().getFullYear();

// Select the service automatically when clicked
const serviceSelect = document.getElementById("service");

document.querySelectorAll("[data-service]").forEach(link => {
  link.addEventListener("click", () => {
    serviceSelect.value = link.dataset.service;
  });
});

// Contact form: prepare a WhatsApp message
document.getElementById("contactForm").addEventListener("submit", event => {
  event.preventDefault();

  const name = document.getElementById("name").value.trim();
  const phone = document.getElementById("phone").value.trim();
  const service = serviceSelect.value;
  const message = document.getElementById("message").value.trim();
  const feedback = document.getElementById("formMessage");

  feedback.textContent = "";

  if (!name || !service || !message) {
    feedback.textContent = "Please complete all required fields.";
    return;
  }

  if (!/^\d{10,15}$/.test(BUSINESS_WHATSAPP) ||
      BUSINESS_WHATSAPP === "25470000000") {
    feedback.textContent =
      "Please add your real business WhatsApp number in the JavaScript section.";
    return;
  }

  const whatsappMessage = [
    "Hello! I found your website and would like to enquire.",
    "",
    `Name: ${name}`,
    phone ? `My phone: ${phone}` : "",
    `Service: ${service}`,
    `Message: ${message}`
  ].filter(Boolean).join("\n");

  const whatsappNumber = BUSINESS_WHATSAPP.replace(/\D/g, "");
  const url = `https://wa.me/${whatsappNumber}?text=${encodeURIComponent(whatsappMessage)}`;

  const newWindow = window.open(url, "_blank", "noopener,noreferrer");
  if (!newWindow) {
    window.location.href = url;
  }
});
</script>

</body>
</html>
