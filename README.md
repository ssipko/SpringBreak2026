# SpringBreak2026
# The Texas Takeover of Breckenridge
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🏔️ The Texas Takeover — Breckenridge 2026</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Outfit:wght@300;400;500;600;700&family=Permanent+Marker&display=swap" rel="stylesheet">
<style>
:root {
  --ice-dark: #1a3a5c;
  --ice-mid: #2d6a9f;
  --ice-light: #5ba3d9;
  --ice-pale: #b8daf0;
  --ice-frost: #e3f0fa;
  --snow: #f5f9fc;
  --white: #ffffff;
  --texas-orange: #e8732a;
  --texas-red: #c0392b;
  --gold: #f0c040;
  --night: #0d1b2a;
  --glass: rgba(255,255,255,0.12);
  --glass-border: rgba(255,255,255,0.2);
}

* { margin:0; padding:0; box-sizing:border-box; }

html { scroll-behavior: smooth; }

body {
  font-family: 'Outfit', sans-serif;
  background: var(--snow);
  color: var(--ice-dark);
  overflow-x: hidden;
}

/* ============ SNOWFALL ANIMATION ============ */
.snowfall {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  pointer-events: none;
  z-index: 9999;
  overflow: hidden;
}
.snowflake {
  position: absolute;
  top: -10px;
  color: rgba(255,255,255,0.7);
  font-size: 1rem;
  animation: snowfallAnim linear infinite;
  text-shadow: 0 0 3px rgba(200,220,240,0.5);
}
@keyframes snowfallAnim {
  0% { transform: translateY(-10px) rotate(0deg); opacity: 1; }
  100% { transform: translateY(100vh) rotate(360deg); opacity: 0.3; }
}

/* ============ HERO SECTION ============ */
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  background: linear-gradient(160deg, #0d1b2a 0%, #1a3a5c 30%, #2d6a9f 60%, #5ba3d9 85%, #b8daf0 100%);
  overflow: hidden;
  padding: 2rem;
}
.hero::before {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 120px;
  background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1440 120'%3E%3Cpath fill='%23f5f9fc' d='M0,60 C240,120 480,0 720,60 C960,120 1200,0 1440,60 L1440,120 L0,120 Z'/%3E%3C/svg%3E") no-repeat bottom center;
  background-size: cover;
  z-index: 2;
}

.mountain-silhouette {
  position: absolute;
  bottom: 80px; left: 0; right: 0;
  height: 300px;
  background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1440 300'%3E%3Cpolygon fill='%231a3a5c' opacity='0.3' points='0,300 100,140 200,200 350,80 500,180 600,100 720,160 850,60 1000,150 1100,90 1200,170 1350,50 1440,130 1440,300'/%3E%3Cpolygon fill='%232d6a9f' opacity='0.25' points='0,300 80,180 200,240 320,130 450,210 580,140 700,200 830,110 950,190 1100,120 1250,200 1380,100 1440,170 1440,300'/%3E%3C/svg%3E") no-repeat bottom center;
  background-size: cover;
  z-index: 1;
}

.hero-content { position: relative; z-index: 3; }

.hero-badge {
  display: inline-block;
  background: var(--texas-orange);
  color: white;
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.1rem;
  letter-spacing: 3px;
  padding: 0.4rem 1.5rem;
  border-radius: 30px;
  margin-bottom: 1.5rem;
  animation: fadeSlideDown 1s ease forwards;
  opacity: 0;
}

.hero h1 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(3.5rem, 10vw, 8rem);
  color: white;
  line-height: 0.95;
  letter-spacing: 4px;
  text-shadow: 0 4px 30px rgba(0,0,0,0.3);
  animation: fadeSlideDown 1s 0.2s ease forwards;
  opacity: 0;
}
.hero h1 span {
  display: block;
  font-family: 'Permanent Marker', cursive;
  font-size: 0.45em;
  color: var(--texas-orange);
  letter-spacing: 6px;
  text-shadow: 0 2px 15px rgba(232,115,42,0.4);
}

.hero-dates {
  font-size: 1.3rem;
  color: var(--ice-pale);
  margin-top: 1rem;
  font-weight: 300;
  letter-spacing: 2px;
  animation: fadeSlideDown 1s 0.4s ease forwards;
  opacity: 0;
}

/* COUNTDOWN */
.countdown-container {
  display: flex;
  gap: 1rem;
  justify-content: center;
  margin-top: 2rem;
  animation: fadeSlideDown 1s 0.6s ease forwards;
  opacity: 0;
}
.countdown-box {
  background: var(--glass);
  backdrop-filter: blur(12px);
  border: 1px solid var(--glass-border);
  border-radius: 16px;
  padding: 1rem 1.2rem;
  min-width: 80px;
  text-align: center;
}
.countdown-box .num {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 2.8rem;
  color: white;
  line-height: 1;
}
.countdown-box .label {
  font-size: 0.7rem;
  color: var(--ice-pale);
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-top: 0.25rem;
}

.hero-cta {
  margin-top: 2.5rem;
  animation: fadeSlideDown 1s 0.8s ease forwards;
  opacity: 0;
}
.hero-cta a {
  display: inline-block;
  background: white;
  color: var(--ice-dark);
  text-decoration: none;
  font-weight: 600;
  padding: 0.9rem 2rem;
  border-radius: 50px;
  font-size: 1rem;
  transition: all 0.3s;
  box-shadow: 0 4px 20px rgba(0,0,0,0.15);
}
.hero-cta a:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 30px rgba(0,0,0,0.25);
  background: var(--texas-orange);
  color: white;
}

@keyframes fadeSlideDown {
  from { opacity:0; transform: translateY(-20px); }
  to { opacity:1; transform: translateY(0); }
}

/* ============ NAV ============ */
.sticky-nav {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: rgba(255,255,255,0.9);
  backdrop-filter: blur(15px);
  border-bottom: 1px solid var(--ice-pale);
  padding: 0.8rem 2rem;
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  flex-wrap: wrap;
}
.sticky-nav a {
  text-decoration: none;
  color: var(--ice-dark);
  font-weight: 500;
  font-size: 0.85rem;
  padding: 0.4rem 1rem;
  border-radius: 20px;
  transition: all 0.3s;
  letter-spacing: 0.5px;
}
.sticky-nav a:hover, .sticky-nav a.active {
  background: var(--ice-dark);
  color: white;
}

/* ============ SECTIONS ============ */
section {
  padding: 4rem 2rem;
  max-width: 1200px;
  margin: 0 auto;
}
.section-header {
  text-align: center;
  margin-bottom: 3rem;
}
.section-header h2 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(2.2rem, 5vw, 3.5rem);
  color: var(--ice-dark);
  letter-spacing: 2px;
}
.section-header p {
  color: var(--ice-mid);
  font-weight: 300;
  font-size: 1.1rem;
  margin-top: 0.5rem;
}
.section-divider {
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, var(--texas-orange), var(--ice-light));
  border-radius: 2px;
  margin: 0.8rem auto 0;
}

/* ============ CALENDAR ============ */
.calendar-section {
  background: linear-gradient(180deg, var(--snow) 0%, var(--ice-frost) 100%);
  padding-bottom: 5rem;
}
.calendar-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 0;
  background: white;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 8px 40px rgba(29,106,159,0.12);
}
.cal-day {
  border-right: 1px solid var(--ice-frost);
  border-bottom: 1px solid var(--ice-frost);
  min-height: 320px;
  display: flex;
  flex-direction: column;
  transition: all 0.3s;
}
.cal-day:hover {
  background: var(--ice-frost);
  transform: scale(1.01);
  z-index: 2;
  box-shadow: 0 4px 20px rgba(0,0,0,0.08);
}
.cal-day-header {
  background: var(--ice-dark);
  color: white;
  text-align: center;
  padding: 0.7rem 0.5rem;
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.1rem;
  letter-spacing: 2px;
}
.cal-day-header .date-num {
  font-size: 0.85rem;
  opacity: 0.7;
  font-family: 'Outfit', sans-serif;
  letter-spacing: 0;
}
.cal-day-body {
  padding: 0.8rem;
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.cal-event {
  background: linear-gradient(135deg, var(--ice-frost), rgba(184,218,240,0.3));
  border-left: 3px solid var(--ice-light);
  border-radius: 8px;
  padding: 0.5rem 0.6rem;
  font-size: 0.78rem;
  line-height: 1.35;
}
.cal-event.highlight {
  background: linear-gradient(135deg, #fef3e2, #fde8d0);
  border-left-color: var(--texas-orange);
}
.cal-event .event-time {
  font-weight: 600;
  color: var(--ice-mid);
  font-size: 0.7rem;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}
.cal-event .event-title {
  font-weight: 600;
  color: var(--ice-dark);
  margin-top: 0.15rem;
}
.cal-event .event-desc {
  color: #5a7a95;
  font-size: 0.72rem;
  margin-top: 0.1rem;
}
.cal-event .event-icon {
  font-size: 1.1rem;
  margin-bottom: 0.15rem;
}

/* ============ NOTES BANNER ============ */
.notes-banner {
  background: linear-gradient(135deg, var(--ice-dark), var(--ice-mid));
  color: white;
  border-radius: 16px;
  padding: 1.5rem 2rem;
  margin-top: 2rem;
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  align-items: center;
  justify-content: center;
}
.notes-banner .note-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.9rem;
  font-weight: 400;
}
.notes-banner .note-icon {
  font-size: 1.3rem;
}

/* ============ HOME BASE ============ */
.home-base-section { background: var(--white); }
.home-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}
.home-card {
  background: var(--snow);
  border-radius: 16px;
  padding: 1.8rem;
  border: 1px solid var(--ice-pale);
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}
.home-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--ice-light), var(--ice-mid));
}
.home-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 30px rgba(29,106,159,0.1);
}
.home-card .card-icon { font-size: 2rem; margin-bottom: 0.8rem; }
.home-card h3 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.4rem;
  letter-spacing: 1px;
  color: var(--ice-dark);
  margin-bottom: 0.6rem;
}
.home-card p {
  font-size: 0.9rem;
  line-height: 1.6;
  color: #4a6a80;
}
.home-card .card-detail {
  font-size: 0.82rem;
  color: var(--ice-mid);
  margin-top: 0.4rem;
  font-weight: 500;
}

/* ============ CONTACT STRIP ============ */
.contact-strip {
  background: linear-gradient(135deg, var(--texas-orange), #d4621e);
  border-radius: 16px;
  padding: 1.5rem 2rem;
  margin-top: 2rem;
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  align-items: center;
  justify-content: center;
  color: white;
}
.contact-item {
  text-align: center;
}
.contact-item .ci-label {
  font-size: 0.7rem;
  text-transform: uppercase;
  letter-spacing: 2px;
  opacity: 0.8;
}
.contact-item .ci-value {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.3rem;
  letter-spacing: 1px;
}
.contact-item a {
  color: white;
  text-decoration: none;
}

/* ============ DINING ============ */
.dining-section { background: var(--snow); }
.dining-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  gap: 1.5rem;
}
.dining-card {
  background: white;
  border-radius: 16px;
  padding: 1.5rem;
  border: 1px solid var(--ice-pale);
  display: flex;
  gap: 1rem;
  align-items: flex-start;
  transition: all 0.3s;
}
.dining-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 25px rgba(0,0,0,0.08);
}
.dining-card .d-icon { font-size: 2.2rem; flex-shrink: 0; margin-top: 0.2rem; }
.dining-card .d-body h3 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.3rem;
  letter-spacing: 1px;
  color: var(--ice-dark);
}
.dining-card .d-style {
  display: inline-block;
  background: var(--ice-frost);
  color: var(--ice-mid);
  font-size: 0.72rem;
  font-weight: 600;
  padding: 0.2rem 0.6rem;
  border-radius: 10px;
  margin: 0.3rem 0;
  letter-spacing: 0.5px;
  text-transform: uppercase;
}
.dining-card .d-desc {
  font-size: 0.88rem;
  color: #4a6a80;
  line-height: 1.5;
  margin-top: 0.3rem;
}

/* ============ ACTIVITIES ============ */
.activities-section { background: var(--white); }
.act-columns {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
}
.act-column h3 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.5rem;
  letter-spacing: 1px;
  color: var(--ice-dark);
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}
.act-item {
  background: var(--snow);
  border-radius: 12px;
  padding: 1rem 1.2rem;
  margin-bottom: 0.8rem;
  border: 1px solid var(--ice-pale);
  transition: all 0.3s;
}
.act-item:hover { border-color: var(--ice-light); transform: translateX(4px); }
.act-item h4 {
  font-weight: 600;
  color: var(--ice-dark);
  font-size: 0.95rem;
}
.act-item p {
  font-size: 0.85rem;
  color: #5a7a95;
  line-height: 1.5;
  margin-top: 0.3rem;
}

/* ============ PACKING LIST ============ */
.packing-section {
  background: linear-gradient(180deg, var(--snow), var(--ice-frost));
}
.packing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1.5rem;
}
.packing-category {
  background: white;
  border-radius: 16px;
  padding: 1.5rem;
  border: 1px solid var(--ice-pale);
}
.packing-category h3 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.2rem;
  letter-spacing: 1px;
  color: var(--ice-dark);
  margin-bottom: 0.8rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}
.pack-item {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  padding: 0.35rem 0;
  font-size: 0.88rem;
  color: #4a6a80;
  cursor: pointer;
  transition: all 0.2s;
}
.pack-item:hover { color: var(--ice-dark); }
.pack-item input[type="checkbox"] {
  accent-color: var(--texas-orange);
  width: 16px;
  height: 16px;
  cursor: pointer;
}
.pack-item.checked { text-decoration: line-through; opacity: 0.5; }

/* ============ LINKS / RESOURCES ============ */
.links-section { background: var(--white); }
.links-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}
.link-card {
  display: flex;
  align-items: center;
  gap: 1rem;
  background: var(--snow);
  border: 1px solid var(--ice-pale);
  border-radius: 14px;
  padding: 1.2rem 1.5rem;
  text-decoration: none;
  color: var(--ice-dark);
  transition: all 0.3s;
}
.link-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 25px rgba(0,0,0,0.08);
  border-color: var(--ice-light);
}
.link-card .link-icon { font-size: 2rem; }
.link-card .link-body h3 {
  font-weight: 600;
  font-size: 0.95rem;
}
.link-card .link-body p {
  font-size: 0.78rem;
  color: var(--ice-mid);
  margin-top: 0.15rem;
}
.link-card .arrow {
  margin-left: auto;
  font-size: 1.2rem;
  color: var(--ice-light);
  transition: transform 0.3s;
}
.link-card:hover .arrow { transform: translateX(4px); }

/* ============ SPA ============ */
.spa-banner {
  background: linear-gradient(135deg, #1a3a5c, #2d6a9f);
  border-radius: 20px;
  padding: 2.5rem;
  color: white;
  text-align: center;
  margin: 2rem 0;
}
.spa-banner h3 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 2rem;
  letter-spacing: 2px;
}
.spa-banner p {
  font-weight: 300;
  max-width: 600px;
  margin: 0.8rem auto;
  line-height: 1.6;
  opacity: 0.9;
}
.spa-banner .spa-detail {
  margin-top: 1rem;
  font-size: 0.9rem;
  opacity: 0.8;
}
.spa-banner a {
  display: inline-block;
  margin-top: 1rem;
  background: white;
  color: var(--ice-dark);
  padding: 0.7rem 1.8rem;
  border-radius: 30px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s;
}
.spa-banner a:hover { background: var(--texas-orange); color: white; }

/* ============ FOOTER ============ */
footer {
  background: var(--night);
  color: white;
  text-align: center;
  padding: 3rem 2rem;
}
footer h3 {
  font-family: 'Permanent Marker', cursive;
  font-size: 1.8rem;
  color: var(--texas-orange);
  margin-bottom: 0.5rem;
}
footer p {
  font-weight: 300;
  opacity: 0.7;
  font-size: 0.9rem;
}
footer .footer-links {
  margin-top: 1.5rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}
footer .footer-links a {
  color: var(--ice-pale);
  text-decoration: none;
  font-size: 0.85rem;
  transition: color 0.3s;
}
footer .footer-links a:hover { color: var(--texas-orange); }

/* ============ SCROLL ANIMATIONS ============ */
.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* ============ RESPONSIVE ============ */
@media (max-width: 900px) {
  .calendar-grid {
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  }
  .cal-day { min-height: 250px; }
}
@media (max-width: 600px) {
  .calendar-grid {
    grid-template-columns: 1fr 1fr;
  }
  .cal-day { min-height: 220px; }
  section { padding: 3rem 1rem; }
  .countdown-box { min-width: 60px; padding: 0.7rem; }
  .countdown-box .num { font-size: 2rem; }
  .sticky-nav { gap: 0.3rem; padding: 0.6rem 0.8rem; }
  .sticky-nav a { font-size: 0.75rem; padding: 0.3rem 0.6rem; }
  .dining-grid { grid-template-columns: 1fr; }
  .notes-banner { flex-direction: column; text-align: center; }
}
</style>
</head>
<body>

<!-- SNOWFALL -->
<div class="snowfall" id="snowfall"></div>

<!-- ============ HERO ============ -->
<section class="hero" id="top">
  <div class="mountain-silhouette"></div>
  <div class="hero-content">
    <div class="hero-badge">🤠 SPRING BREAK 2026</div>
    <h1>
      <span>The Texas Takeover</span>
      BRECKENRIDGE
    </h1>
    <div class="hero-dates">MARCH 8 – 15, 2026 &nbsp;·&nbsp; Grand Colorado on Peak 8</div>

    <div class="countdown-container" id="countdown">
      <div class="countdown-box">
        <div class="num" id="cd-days">--</div>
        <div class="label">Days</div>
      </div>
      <div class="countdown-box">
        <div class="num" id="cd-hours">--</div>
        <div class="label">Hours</div>
      </div>
      <div class="countdown-box">
        <div class="num" id="cd-mins">--</div>
        <div class="label">Mins</div>
      </div>
      <div class="countdown-box">
        <div class="num" id="cd-secs">--</div>
        <div class="label">Secs</div>
      </div>
    </div>

    <div class="hero-cta">
      <a href="#calendar">See the Full Schedule ↓</a>
    </div>
  </div>
</section>

<!-- ============ STICKY NAV ============ -->
<nav class="sticky-nav">
  <a href="#calendar">📅 Calendar</a>
  <a href="#homebase">🏨 Home Base</a>
  <a href="#dining">🍴 Dining</a>
  <a href="#activities">🌲 Activities</a>
  <a href="#packing">🎒 Packing</a>
  <a href="#links">🔗 Links</a>
</nav>

<!-- ============ CALENDAR ============ -->
<section class="calendar-section" id="calendar">
  <div class="section-header reveal">
    <h2>📅 The Week at a Glance</h2>
    <p>Your day-by-day adventure plan — Spring Breck 2026</p>
    <div class="section-divider"></div>
  </div>

  <div class="calendar-grid reveal">
    <!-- SUNDAY 3/8 -->
    <div class="cal-day">
      <div class="cal-day-header">Sunday <div class="date-num">March 8</div></div>
      <div class="cal-day-body">
        <div class="cal-event highlight">
          <div class="event-icon">✅</div>
          <div class="event-time">4:00 PM</div>
          <div class="event-title">Check-In & Pick Up Skis</div>
        </div>
        <div class="cal-event">
          <div class="event-icon">🍝</div>
          <div class="event-title">Dinner In!</div>
          <div class="event-desc">DD's Italian Night</div>
        </div>
        <div class="cal-event highlight">
          <div class="event-icon">🏁</div>
          <div class="event-title">Welcome!</div>
          <div class="event-desc">Capture the Flag & Games!</div>
        </div>
      </div>
    </div>

    <!-- MONDAY 3/9 -->
    <div class="cal-day">
      <div class="cal-day-header">Monday <div class="date-num">March 9</div></div>
      <div class="cal-day-body">
        <div class="cal-event">
          <div class="event-icon">⛷️</div>
          <div class="event-title">Lunch on the Mountain</div>
        </div>
        <div class="cal-event highlight">
          <div class="event-time">3:30 PM</div>
          <div class="event-title">Grand Colorado Lobby Happy Hour</div>
          <div class="event-desc">Stay & Play!</div>
        </div>
        <div class="cal-event">
          <div class="event-icon">🔥</div>
          <div class="event-title">Grillin' & Chillin'</div>
        </div>
        <div class="cal-event">
          <div class="event-icon">🎬</div>
          <div class="event-time">9:00 PM</div>
          <div class="event-title">Movie Room Reserved</div>
        </div>
      </div>
    </div>

    <!-- TUESDAY 3/10 -->
    <div class="cal-day">
      <div class="cal-day-header">Tuesday <div class="date-num">March 10</div></div>
      <div class="cal-day-body">
        <div class="cal-event">
          <div class="event-icon">🍲</div>
          <div class="event-time">11:30 – 1:00</div>
          <div class="event-title">Soup-er Subs!</div>
          <div class="event-desc">Rolling Lunch</div>
        </div>
        <div class="cal-event highlight">
          <div class="event-icon">🛍️</div>
          <div class="event-title">Shopping Downtown!</div>
          <div class="event-desc">Ruby Jane's · Valleygirl Beloved · Olive Fusion</div>
        </div>
        <div class="cal-event">
          <div class="event-icon">🍕</div>
          <div class="event-time">~5:00 PM</div>
          <div class="event-title">Eric's Downstairs</div>
        </div>
      </div>
    </div>

    <!-- WEDNESDAY 3/11 -->
    <div class="cal-day">
      <div class="cal-day-header">Wednesday <div class="date-num">March 11</div></div>
      <div class="cal-day-body">
        <div class="cal-event highlight">
          <div class="event-icon">🎂</div>
          <div class="event-time">5:30 PM</div>
          <div class="event-title">Adult Dinner @ Breck Distillery</div>
          <div class="event-desc">Sean's Birthday Celebration!</div>
        </div>
      </div>
    </div>

    <!-- THURSDAY 3/12 -->
    <div class="cal-day">
      <div class="cal-day-header">Thursday <div class="date-num">March 12</div></div>
      <div class="cal-day-body">
        <div class="cal-event">
          <div class="event-icon">🫔</div>
          <div class="event-time">11:30 – 1:00</div>
          <div class="event-title">Nach-Yo Ordinary Rolling Lunch</div>
        </div>
        <div class="cal-event highlight">
          <div class="event-icon">🃏</div>
          <div class="event-time">7:30 PM</div>
          <div class="event-title">Poker Night</div>
        </div>
      </div>
    </div>

    <!-- FRIDAY 3/13 -->
    <div class="cal-day">
      <div class="cal-day-header">Friday <div class="date-num">March 13</div></div>
      <div class="cal-day-body">
        <div class="cal-event highlight">
          <div class="event-icon">🍽️</div>
          <div class="event-time">5:00 PM</div>
          <div class="event-title">Dinner @ Rootstalk</div>
        </div>
      </div>
    </div>

    <!-- SATURDAY 3/14 -->
    <div class="cal-day">
      <div class="cal-day-header">Saturday <div class="date-num">March 14</div></div>
      <div class="cal-day-body">
        <div class="cal-event highlight">
          <div class="event-icon">☘️</div>
          <div class="event-title">St. Patrick's Week!</div>
          <div class="event-desc">Green beer & bagpipers on Main St.</div>
        </div>
        <div class="cal-event">
          <div class="event-icon">🎶</div>
          <div class="event-title">Après at the Overlook</div>
          <div class="event-desc">Live music at 11,274 ft — Peak 9</div>
        </div>
        <div class="cal-event">
          <div class="event-icon">⛷️</div>
          <div class="event-title">Last Full Ski Day!</div>
        </div>
      </div>
    </div>

    <!-- SUNDAY 3/15 -->
    <div class="cal-day">
      <div class="cal-day-header">Sunday <div class="date-num">March 15</div></div>
      <div class="cal-day-body">
        <div class="cal-event highlight">
          <div class="event-icon">🏠</div>
          <div class="event-title">Check-Out Day</div>
          <div class="event-desc">Safe travels home, y'all! 🤠</div>
        </div>
      </div>
    </div>
  </div>

  <!-- NOTES BANNER -->
  <div class="notes-banner reveal">
    <div class="note-item"><span class="note-icon">🍷</span> Free Breck Wine Tasting</div>
    <div class="note-item"><span class="note-icon">🚐</span> Free Shuttle — Download the App!</div>
    <div class="note-item"><span class="note-icon">🎬</span> Movie Rooms can be booked after Monday</div>
  </div>
</section>

<!-- ============ HOME BASE ============ -->
<section class="home-base-section" id="homebase">
  <div class="section-header reveal">
    <h2>🏨 Your Home Base</h2>
    <p>Grand Colorado on Peak 8 — One of the most coveted addresses in Breckenridge</p>
    <div class="section-divider"></div>
  </div>

  <div class="home-grid reveal">
    <div class="home-card">
      <div class="card-icon">🌊</div>
      <h3>The Grotto</h3>
      <p>An exclusive, adult-only sanctuary within the Infinity Spa featuring a stunning waterfall hot tub, sauna, and steam room.</p>
    </div>
    <div class="home-card">
      <div class="card-icon">🏊</div>
      <h3>Aquatics</h3>
      <p>Multiple heated indoor/outdoor pools and a dedicated children's area with a waterslide. Perfect for après-ski!</p>
    </div>
    <div class="home-card">
      <div class="card-icon">🎬</div>
      <h3>Entertainment</h3>
      <p>Private movie theaters (reservation required), a family game room, and the Gr8 Escape Room (additional fee).</p>
    </div>
    <div class="home-card">
      <div class="card-icon">💪</div>
      <h3>Fitness & Sport</h3>
      <p>Fully equipped workout facility, on-site ice skating rink, and complimentary slopeside ski lockers.</p>
    </div>
    <div class="home-card">
      <div class="card-icon">⛷️</div>
      <h3>Mountain Access</h3>
      <p>Ski-in/Ski-out — steps from the Colorado SuperChair and Rocky Mountain SuperChair. Breck Sports on-site for gear.</p>
    </div>
    <div class="home-card">
      <div class="card-icon">🚡</div>
      <h3>BreckConnect Gondola</h3>
      <p>A free, scenic 10-minute ride connecting Peak 8 to Peak 7 and the center of town. No car needed!</p>
    </div>
  </div>

  <!-- CONTACT STRIP -->
  <div class="contact-strip reveal">
    <div class="contact-item">
      <div class="ci-label">Address</div>
      <div class="ci-value"><a href="https://maps.google.com/?q=1627+Ski+Hill+Road+Breckenridge+CO+80424" target="_blank">1627 Ski Hill Rd, Breckenridge</a></div>
    </div>
    <div class="contact-item">
      <div class="ci-label">Front Desk (24/7)</div>
      <div class="ci-value"><a href="tel:9705473693">(970) 547-3693</a></div>
    </div>
    <div class="contact-item">
      <div class="ci-label">On-Site Dining</div>
      <div class="ci-value"><a href="tel:9705478785">Robbie's Tavern</a></div>
    </div>
  </div>

  <!-- ON-SITE DINING -->
  <div style="margin-top:2rem;" class="reveal">
    <div class="home-grid">
      <div class="home-card">
        <div class="card-icon">🍽️</div>
        <h3>Robbie's Tavern</h3>
        <p>The only locally owned slopeside bistro at the base. Refined American comfort food — try the flatbreads on the patio by the fire table.</p>
        <div class="card-detail">📞 (970) 547-8785</div>
      </div>
      <div class="home-card">
        <div class="card-icon">🍸</div>
        <h3>Elev8 Lounge</h3>
        <p>A sophisticated rooftop bar offering the best panoramic views of the Ten Mile Range. Perfect for sunset drinks.</p>
      </div>
      <div class="home-card">
        <div class="card-icon">☕</div>
        <h3>Ullr Café</h3>
        <p>Your go-to for a quick morning espresso or a grab-and-go sandwich before hitting the slopes.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ DINING ============ -->
<section class="dining-section" id="dining">
  <div class="section-header reveal">
    <h2>🍴 Dining Recommendations</h2>
    <p>From casual burgers to historic fine dining — the best spots in Breck</p>
    <div class="section-divider"></div>
  </div>

  <div class="dining-grid reveal">
    <div class="dining-card">
      <div class="d-icon">🎮</div>
      <div class="d-body">
        <h3>Downstairs at Eric's</h3>
        <div class="d-style">Family Casual</div>
        <p class="d-desc">An iconic basement spot with an arcade, legendary wings, and 30+ beers on tap.</p>
      </div>
    </div>
    <div class="dining-card">
      <div class="d-icon">🍔</div>
      <div class="d-body">
        <h3>Empire Burger</h3>
        <div class="d-style">Modern Burger Bar</div>
        <p class="d-desc">Consistently voted "Best Burger in Breck." Try the truffle aioli dip for your fries.</p>
      </div>
    </div>
    <div class="dining-card">
      <div class="d-icon">🍕</div>
      <div class="d-body">
        <h3>Giampietro's</h3>
        <div class="d-style">Italian / Pizzeria</div>
        <p class="d-desc">Authentic New York-style pizza and handmade pasta. Usually has a wait — get there early!</p>
      </div>
    </div>
    <div class="dining-card">
      <div class="d-icon">🥩</div>
      <div class="d-body">
        <h3>Briar Rose</h3>
        <div class="d-style">Steakhouse</div>
        <p class="d-desc">A historic, upscale landmark. The back bar "Saloon" serves an incredible prime rib sandwich.</p>
      </div>
    </div>
    <div class="dining-card">
      <div class="d-icon">🍺</div>
      <div class="d-body">
        <h3>Breckenridge Brewery</h3>
        <div class="d-style">Brewpub</div>
        <p class="d-desc">A Main Street staple. Great views of the mountain and classic pub fare paired with local ales.</p>
      </div>
    </div>
    <div class="dining-card">
      <div class="d-icon">🥞</div>
      <div class="d-body">
        <h3>Blue Moose</h3>
        <div class="d-style">Breakfast</div>
        <p class="d-desc">The locals' favorite for a hearty breakfast before hitting the slopes. Cash only / local vibe.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ ACTIVITIES ============ -->
<section class="activities-section" id="activities">
  <div class="section-header reveal">
    <h2>🌲 Beyond the Slopes</h2>
    <p>There's way more to Breck than just skiing</p>
    <div class="section-divider"></div>
  </div>

  <div class="act-columns reveal">
    <div class="act-column">
      <h3>⛰️ Adventure & Nature</h3>
      <div class="act-item">
        <h4>Gold Runner Alpine Coaster</h4>
        <p>Located at the base of Peak 8 — 2,500 feet of elevated track winding through the forest.</p>
      </div>
      <div class="act-item">
        <h4>Snowmobile Tours</h4>
        <p>Head into the Ten Mile Range for high-alpine views that skiers never see.</p>
      </div>
      <div class="act-item">
        <h4>Ski with a Ranger</h4>
        <p>Thursdays at 11 AM — meet at Peak 7 Independence Chair for a free ecology tour.</p>
      </div>
    </div>

    <div class="act-column">
      <h3>🎨 Arts & History</h3>
      <div class="act-item">
        <h4>BreckCreate Arts District</h4>
        <p>Renovated historic structures housing ceramics, glassblowing, and painting workshops.</p>
      </div>
      <div class="act-item">
        <h4>Edwin Carter Museum</h4>
        <p>A tiny, fascinating cabin museum dedicated to the "Log Cabin Scientist" of the 1800s.</p>
      </div>
      <div class="act-item">
        <h4>Historic Walking Tour</h4>
        <p>Explore one of the most well-preserved Victorian mining towns in the Rockies.</p>
      </div>
    </div>

    <div class="act-column">
      <h3>🏋️ Recreation Center</h3>
      <div class="act-item">
        <h4>Breckenridge Rec Center</h4>
        <p>88,000 sq. ft. including indoor rock wall, tennis courts, and a massive aquatics center.</p>
      </div>
      <div class="act-item">
        <h4>Pickleball Drop-In</h4>
        <p>Daily 12:00 – 3:00 PM. Plus yoga, body pump, and more fitness classes.</p>
      </div>
      <div class="act-item">
        <h4>📍 880 Airport Rd, Breckenridge</h4>
        <p>Open to the public — great option for rest days!</p>
      </div>
    </div>
  </div>

  <!-- SPA BANNER -->
  <div class="spa-banner reveal">
    <h3>💆 Infinity Spa — On Property</h3>
    <p>The perfect way to recover from "ski legs." The Himalayan Salt Stone Massage is highly recommended for altitude adjustment.</p>
    <div class="spa-detail">🕗 8:00 AM – 8:00 PM &nbsp;·&nbsp; 📞 (970) 547-8795</div>
    <a href="https://www.grandcolorado.com" target="_blank">Book at GrandColorado.com →</a>
  </div>

  <!-- FEATURED EVENTS -->
  <div style="margin-top:3rem;" class="reveal">
    <div class="section-header">
      <h2>🎉 Featured Events During Your Stay</h2>
      <div class="section-divider"></div>
    </div>
    <div class="home-grid">
      <div class="home-card">
        <div class="card-icon">⛷️</div>
        <h3>Summit Skimo Series: Peak 9 Ascent</h3>
        <p>Thursday, March 12 — A high-energy ski mountaineering race. Whether you're a pro or first-timer, it's a great way to experience the uphill community.</p>
      </div>
      <div class="home-card" style="--before-bg: linear-gradient(90deg, #2ecc71, #27ae60);">
        <div class="card-icon">☘️</div>
        <h3>St. Patrick's Week</h3>
        <p>March 13–15 on Main Street. Look for bagpipers, green beer, and head to Napper Tandy's for authentic Irish spirit. Breck Brewery usually debuts a seasonal nitro stout.</p>
      </div>
      <div class="home-card">
        <div class="card-icon">🎶</div>
        <h3>Après at the Overlook</h3>
        <p>March 14–15 weekend at Overlook Lodge, Peak 9. Live music at 11,274 feet — one of the highest concert venues in North America with outdoor BBQ specials.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ PACKING LIST ============ -->
<section class="packing-section" id="packing">
  <div class="section-header reveal">
    <h2>🎒 Packing Checklist</h2>
    <p>Spring skiing means warm days and cold mornings — layer up!</p>
    <div class="section-divider"></div>
  </div>

  <div class="packing-grid reveal">
    <div class="packing-category">
      <h3>⛷️ Ski Gear</h3>
      <label class="pack-item"><input type="checkbox"> Ski jacket & pants</label>
      <label class="pack-item"><input type="checkbox"> Base layers (top & bottom)</label>
      <label class="pack-item"><input type="checkbox"> Ski socks (wool)</label>
      <label class="pack-item"><input type="checkbox"> Helmet</label>
      <label class="pack-item"><input type="checkbox"> Goggles</label>
      <label class="pack-item"><input type="checkbox"> Gloves / mittens</label>
      <label class="pack-item"><input type="checkbox"> Neck gaiter / balaclava</label>
      <label class="pack-item"><input type="checkbox"> Hand & toe warmers</label>
    </div>
    <div class="packing-category">
      <h3>👕 Clothing</h3>
      <label class="pack-item"><input type="checkbox"> Warm fleece / puffy jacket</label>
      <label class="pack-item"><input type="checkbox"> Casual dinner outfits</label>
      <label class="pack-item"><input type="checkbox"> Comfortable walking shoes</label>
      <label class="pack-item"><input type="checkbox"> Winter boots</label>
      <label class="pack-item"><input type="checkbox"> Beanie / warm hat</label>
      <label class="pack-item"><input type="checkbox"> Sunglasses</label>
      <label class="pack-item"><input type="checkbox"> Swimsuit (pools & hot tubs!)</label>
      <label class="pack-item"><input type="checkbox"> Poker night outfit 🃏</label>
    </div>
    <div class="packing-category">
      <h3>🧴 Essentials</h3>
      <label class="pack-item"><input type="checkbox"> Sunscreen SPF 50+</label>
      <label class="pack-item"><input type="checkbox"> Lip balm with SPF</label>
      <label class="pack-item"><input type="checkbox"> Moisturizer (dry altitude!)</label>
      <label class="pack-item"><input type="checkbox"> Water bottle (hydrate!)</label>
      <label class="pack-item"><input type="checkbox"> Medications / vitamins</label>
      <label class="pack-item"><input type="checkbox"> Phone charger / portable battery</label>
      <label class="pack-item"><input type="checkbox"> Cash (Blue Moose is cash only)</label>
    </div>
    <div class="packing-category">
      <h3>🏔️ Altitude Tips</h3>
      <label class="pack-item"><input type="checkbox"> Drink LOTS of water</label>
      <label class="pack-item"><input type="checkbox"> Take it easy Day 1</label>
      <label class="pack-item"><input type="checkbox"> Limit alcohol first night</label>
      <label class="pack-item"><input type="checkbox"> Bring electrolyte packets</label>
      <label class="pack-item"><input type="checkbox"> Ibuprofen for headaches</label>
      <label class="pack-item"><input type="checkbox"> Eat carbs & protein</label>
      <label class="pack-item"><input type="checkbox"> Download Shuttle App</label>
    </div>
  </div>
</section>

<!-- ============ LINKS ============ -->
<section class="links-section" id="links">
  <div class="section-header reveal">
    <h2>🔗 Quick Links & Resources</h2>
    <p>Everything you need at your fingertips</p>
    <div class="section-divider"></div>
  </div>

  <div class="links-grid reveal">
    <a class="link-card" href="https://www.breckenridge.com/the-mountain/trail-map.aspx" target="_blank">
      <div class="link-icon">🗺️</div>
      <div class="link-body">
        <h3>Breckenridge Ski Trail Map</h3>
        <p>Interactive trail map with all peaks & lifts</p>
      </div>
      <div class="arrow">→</div>
    </a>
    <a class="link-card" href="https://www.breckenridge.com/the-mountain/mountain-conditions/snow-and-weather-report.aspx" target="_blank">
      <div class="link-icon">🌨️</div>
      <div class="link-body">
        <h3>Snow & Weather Report</h3>
        <p>Live conditions, snowfall & forecast</p>
      </div>
      <div class="arrow">→</div>
    </a>
    <a class="link-card" href="https://www.breckenridge.com/the-mountain/mountain-conditions/lift-and-terrain-status.aspx" target="_blank">
      <div class="link-icon">🚡</div>
      <div class="link-body">
        <h3>Lift & Terrain Status</h3>
        <p>Real-time lift & run openings</p>
      </div>
      <div class="arrow">→</div>
    </a>
    <a class="link-card" href="https://www.grandcolorado.com" target="_blank">
      <div class="link-icon">🏨</div>
      <div class="link-body">
        <h3>Grand Colorado on Peak 8</h3>
        <p>Resort info, spa booking & amenities</p>
      </div>
      <div class="arrow">→</div>
    </a>
    <a class="link-card" href="https://www.gobreck.com" target="_blank">
      <div class="link-icon">🏔️</div>
      <div class="link-body">
        <h3>Go Breck — Town Guide</h3>
        <p>Events, dining, shopping & more</p>
      </div>
      <div class="arrow">→</div>
    </a>
    <a class="link-card" href="https://www.breckenridge.com/plan-your-trip/shuttle-bus-services.aspx" target="_blank">
      <div class="link-icon">🚐</div>
      <div class="link-body">
        <h3>Free Shuttle / Transit</h3>
        <p>Routes, schedules & app download</p>
      </div>
      <div class="arrow">→</div>
    </a>
    <a class="link-card" href="https://www.breckcreate.org" target="_blank">
      <div class="link-icon">🎨</div>
      <div class="link-body">
        <h3>BreckCreate Arts District</h3>
        <p>Workshops, galleries & events</p>
      </div>
      <div class="arrow">→</div>
    </a>
    <a class="link-card" href="https://www.breckenridgerecreation.com" target="_blank">
      <div class="link-icon">🏋️</div>
      <div class="link-body">
        <h3>Recreation Center</h3>
        <p>Pool, rock wall, pickleball & classes</p>
      </div>
      <div class="arrow">→</div>
    </a>
    <a class="link-card" href="https://maps.google.com/?q=1627+Ski+Hill+Road+Breckenridge+CO+80424" target="_blank">
      <div class="link-icon">📍</div>
      <div class="link-body">
        <h3>Google Maps — Grand Colorado</h3>
        <p>Directions & navigation</p>
      </div>
      <div class="arrow">→</div>
    </a>
  </div>
</section>

<!-- ============ FOOTER ============ -->
<footer>
  <h3>🤠 The Texas Takeover 🏔️</h3>
  <p>Breckenridge, CO &nbsp;·&nbsp; March 8–15, 2026 &nbsp;·&nbsp; Grand Colorado on Peak 8</p>
  <div class="footer-links">
    <a href="#top">Back to Top</a>
    <a href="#calendar">Calendar</a>
    <a href="#homebase">Home Base</a>
    <a href="#dining">Dining</a>
    <a href="#activities">Activities</a>
    <a href="#packing">Packing</a>
    <a href="#links">Quick Links</a>
  </div>
</footer>

<script>
// ============ COUNTDOWN TIMER ============
function updateCountdown() {
  const tripDate = new Date('2026-03-08T16:00:00-07:00');
  const now = new Date();
  const diff = tripDate - now;

  if (diff <= 0) {
    document.getElementById('cd-days').textContent = '🎉';
    document.getElementById('cd-hours').textContent = "IT'S";
    document.getElementById('cd-mins').textContent = 'GO';
    document.getElementById('cd-secs').textContent = 'TIME';
    return;
  }

  const days = Math.floor(diff / (1000*60*60*24));
  const hours = Math.floor((diff % (1000*60*60*24)) / (1000*60*60));
  const mins = Math.floor((diff % (1000*60*60)) / (1000*60));
  const secs = Math.floor((diff % (1000*60)) / 1000);

  document.getElementById('cd-days').textContent = days;
  document.getElementById('cd-hours').textContent = String(hours).padStart(2,'0');
  document.getElementById('cd-mins').textContent = String(mins).padStart(2,'0');
  document.getElementById('cd-secs').textContent = String(secs).padStart(2,'0');
}
updateCountdown();
setInterval(updateCountdown, 1000);

// ============ SNOWFALL ============
function createSnowfall() {
  const container = document.getElementById('snowfall');
  const flakes = ['❄','❅','❆','✦','·'];
  for (let i = 0; i < 35; i++) {
    const flake = document.createElement('div');
    flake.className = 'snowflake';
    flake.textContent = flakes[Math.floor(Math.random()*flakes.length)];
    flake.style.left = Math.random()*100 + '%';
    flake.style.fontSize = (Math.random()*0.8 + 0.5) + 'rem';
    flake.style.animationDuration = (Math.random()*8 + 6) + 's';
    flake.style.animationDelay = (Math.random()*10) + 's';
    flake.style.opacity = Math.random()*0.6 + 0.2;
    container.appendChild(flake);
  }
}
createSnowfall();

// ============ SCROLL REVEAL ============
const reveals = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1 });
reveals.forEach(el => observer.observe(el));

// ============ PACKING CHECKLIST ============
document.querySelectorAll('.pack-item input').forEach(cb => {
  cb.addEventListener('change', function() {
    this.closest('.pack-item').classList.toggle('checked', this.checked);
  });
});

// ============ ACTIVE NAV ============
const sections = document.querySelectorAll('section[id]');
const navLinks = document.querySelectorAll('.sticky-nav a');
window.addEventListener('scroll', () => {
  let current = '';
  sections.forEach(section => {
    const top = section.offsetTop - 120;
    if (pageYOffset >= top) current = section.getAttribute('id');
  });
  navLinks.forEach(link => {
    link.classList.remove('active');
    if (link.getAttribute('href') === '#' + current) link.classList.add('active');
  });
});
</script>

</body>
</html>
