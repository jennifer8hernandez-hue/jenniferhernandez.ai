/* ============================================
   Jennifer Hernandez REALTOR® — Main Stylesheet
   jenniferhernandez.ai
   ============================================ */

/* RESET & ROOT */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --gold:    #BEAF87;
  --gold-dk: #A39060;
  --gold-lt: #D4C9A8;
  --gold-f:  #F5F1E8;
  --dark:    #1A1A1A;
  --ink:     #111;
  --mid:     #444;
  --gray:    #777;
  --light:   #F8F5EE;
  --white:   #fff;
  --serif:   'Playfair Display', Georgia, serif;
  --sans:    'Inter', -apple-system, sans-serif;
  --max:     1180px;
  --t:       0.28s ease;
}

html { scroll-behavior: smooth; font-size: 16px; }

body {
  font-family: var(--sans);
  color: var(--dark);
  background: var(--white);
  line-height: 1.65;
  -webkit-font-smoothing: antialiased;
}

img { display: block; max-width: 100%; height: auto; }
a { color: inherit; text-decoration: none; }
h1, h2, h3, h4 { font-family: var(--serif); line-height: 1.15; font-weight: 600; }
h1 { font-size: clamp(2.2rem, 5vw, 3.75rem); }
h2 { font-size: clamp(1.8rem, 3.5vw, 2.6rem); }
h3 { font-size: clamp(1.1rem, 2vw, 1.35rem); }
p  { font-size: 1rem; color: var(--mid); line-height: 1.85; }

/* LAYOUT UTILITIES */
.wrap    { max-width: var(--max); margin: 0 auto; padding: 0 2rem; }
.section { padding: 5.5rem 0; }
.s-alt   { background: var(--light); }
.s-dark  { background: var(--ink); }
.tc      { text-align: center; }

.eyebrow {
  display: inline-block;
  font-size: .7rem;
  font-weight: 700;
  letter-spacing: .22em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: .75rem;
}
.s-dark .eyebrow { color: var(--gold-lt); }

.rule   { display: block; width: 48px; height: 3px; background: var(--gold); margin: 1rem 0 1.85rem; }
.rule-c { margin-left: auto; margin-right: auto; }

/* BUTTONS */
.btn {
  display: inline-flex;
  align-items: center;
  gap: .5rem;
  padding: .9rem 2rem;
  font-family: var(--sans);
  font-size: .8rem;
  font-weight: 700;
  letter-spacing: .1em;
  text-transform: uppercase;
  border: 2px solid transparent;
  cursor: pointer;
  border-radius: 3px;
  transition: all var(--t);
  white-space: nowrap;
}
.btn-gold  { background: var(--gold); color: var(--dark); border-color: var(--gold); }
.btn-gold:hover { background: var(--gold-dk); border-color: var(--gold-dk); transform: translateY(-2px); box-shadow: 0 8px 22px rgba(190,175,135,.35); }
.btn-dark  { background: var(--dark); color: var(--white); border-color: var(--dark); }
.btn-dark:hover { background: var(--mid); transform: translateY(-2px); }
.btn-ghost { background: transparent; color: var(--white); border-color: rgba(255,255,255,.6); }
.btn-ghost:hover { background: rgba(255,255,255,.1); border-color: var(--white); transform: translateY(-2px); }
.btn-lg { padding: 1.05rem 2.4rem; font-size: .85rem; }

/* ============ NAV ============ */
#jh-nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 9999;
  background: rgba(17,17,17,.97);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(190,175,135,.2);
  transition: box-shadow var(--t);
}
.ni {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: var(--max);
  margin: 0 auto;
  padding: 1rem 2rem;
}
.nb { display: flex; flex-direction: column; }
.nb-name { font-family: var(--serif); font-size: 1.2rem; color: var(--white); line-height: 1.1; }
.nb-tag  { font-size: .66rem; font-weight: 700; letter-spacing: .18em; text-transform: uppercase; color: var(--gold); margin-top: 2px; }
.nl {
  display: flex;
  align-items: center;
  gap: 1.75rem;
  list-style: none;
}
.nl a { font-size: .78rem; font-weight: 600; letter-spacing: .07em; text-transform: uppercase; color: rgba(255,255,255,.72); transition: color var(--t); }
.nl a:hover { color: var(--gold); }
.ncta { color: var(--gold) !important; font-weight: 700 !important; }
.nav-tog {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}
.nav-tog span { display: block; width: 22px; height: 2px; background: var(--white); transition: all var(--t); }

/* ============ HERO ============ */
#jh-hero {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  background: var(--ink);
  padding-top: 72px;
  overflow: hidden;
}
.h-left {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 5rem 3rem 5rem 4rem;
  position: relative;
  z-index: 2;
}
.h-left::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, rgba(17,17,17,1) 55%, rgba(17,17,17,0) 100%);
  z-index: -1;
  pointer-events: none;
}
.h-badge {
  display: inline-flex;
  align-items: center;
  gap: .55rem;
  background: rgba(190,175,135,.12);
  border: 1px solid rgba(190,175,135,.28);
  padding: .4rem .95rem;
  border-radius: 100px;
  margin-bottom: 1.6rem;
  width: fit-content;
}
.h-badge-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--gold); flex-shrink: 0; }
.h-badge-txt { font-size: .7rem; font-weight: 700; letter-spacing: .14em; text-transform: uppercase; color: var(--gold); }

#jh-hero h1   { color: var(--white); margin-bottom: 1.4rem; }
#jh-hero h1 em { font-style: normal; color: var(--gold); }
.h-sub { font-size: 1.05rem; color: rgba(255,255,255,.65); max-width: 460px; line-height: 1.9; margin-bottom: 2.5rem; }
.h-ctas { display: flex; gap: .85rem; flex-wrap: wrap; margin-bottom: 2.75rem; }
.h-contact {
  display: flex;
  align-items: center;
  gap: 1.75rem;
  padding: 1.2rem 1.4rem;
  border: 1px solid rgba(190,175,135,.2);
  background: rgba(255,255,255,.04);
  width: fit-content;
}
.hc-item { display: flex; align-items: center; gap: .6rem; }
.hc-icon {
  width: 34px; height: 34px;
  border-radius: 50%;
  background: rgba(190,175,135,.15);
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
}
.hc-icon svg { width: 15px; height: 15px; stroke: var(--gold); }
.hc-lbl { font-size: .65rem; font-weight: 700; letter-spacing: .1em; text-transform: uppercase; color: rgba(255,255,255,.38); }
.hc-val { font-size: .92rem; font-weight: 700; color: var(--white); margin-top: 1px; }
.hc-div { width: 1px; height: 32px; background: rgba(190,175,135,.18); }

.h-right { position: relative; overflow: hidden; }
.h-right img { width: 100%; height: 100%; object-fit: cover; object-position: center top; }
.h-ov {
  position: absolute; inset: 0;
  background: linear-gradient(90deg, rgba(17,17,17,.55) 0%, transparent 40%),
              linear-gradient(0deg, rgba(17,17,17,.35) 0%, transparent 35%);
}
.h-card {
  position: absolute;
  bottom: 2rem; right: 1.75rem;
  background: rgba(17,17,17,.92);
  backdrop-filter: blur(8px);
  border: 1px solid rgba(190,175,135,.25);
  padding: 1.15rem 1.4rem;
}
.hc-brok { font-size: .66rem; font-weight: 700; letter-spacing: .17em; text-transform: uppercase; color: var(--gold); margin-bottom: .3rem; }
.hc-name { font-family: var(--serif); font-size: 1.1rem; color: var(--white); font-weight: 600; }
.hc-ttl  { font-size: .75rem; color: rgba(255,255,255,.5); margin-top: .15rem; }
.hc-stars { display: flex; align-items: center; gap: .35rem; margin-top: .55rem; }
.hcs { color: #FBBC04; font-size: .8rem; }
.hcc { font-size: .72rem; color: rgba(255,255,255,.45); }

/* ============ STATS ============ */
#jh-stats { background: var(--gold); padding: 1.85rem 0; }
.si {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  max-width: var(--max);
  margin: 0 auto;
  padding: 0 2rem;
}
.stat { text-align: center; padding: 0 1rem; border-right: 1px solid rgba(28,28,28,.14); }
.stat:last-child { border-right: none; }
.sn { font-family: var(--serif); font-size: 2rem; font-weight: 700; color: var(--dark); line-height: 1; }
.sl { font-size: .72rem; font-weight: 700; letter-spacing: .09em; text-transform: uppercase; color: rgba(28,28,28,.6); margin-top: .3rem; }

/* ============ SERVICES ============ */
.svc-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.4rem; margin-top: 3rem; }
.svc {
  padding: 2.25rem 1.75rem;
  border: 1px solid rgba(0,0,0,.08);
  position: relative;
  overflow: hidden;
  transition: all var(--t);
}
.svc::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 3px;
  background: var(--gold);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform var(--t);
}
.svc:hover { transform: translateY(-5px); box-shadow: 0 18px 45px rgba(0,0,0,.07); }
.svc:hover::after { transform: scaleX(1); }
.svc-ico {
  width: 50px; height: 50px;
  border-radius: 50%;
  background: var(--gold-f);
  display: flex; align-items: center; justify-content: center;
  margin-bottom: 1.35rem;
}
.svc-ico svg { width: 22px; height: 22px; stroke: var(--gold-dk); }
.svc h3 { font-size: 1.1rem; color: var(--dark); margin-bottom: .65rem; }
.svc p  { font-size: .88rem; color: var(--gray); line-height: 1.75; }

/* ============ ABOUT ============ */
.about-grid { display: grid; grid-template-columns: 5fr 6fr; gap: 5rem; align-items: center; }
.about-photo { position: relative; }
.aph { aspect-ratio: 4/5; overflow: hidden; background: #2a2a2a; }
.aph img { width: 100%; height: 100%; object-fit: cover; object-position: center top; }
.about-acc { position: absolute; bottom: -1.5rem; right: -1.5rem; width: 180px; height: 180px; background: var(--gold); opacity: .15; z-index: -1; }
.about-chip {
  position: absolute;
  top: 1.75rem; left: -2rem;
  background: var(--ink);
  border-left: 4px solid var(--gold);
  padding: 1.1rem 1.4rem;
}
.acn { font-family: var(--serif); font-size: 1.75rem; font-weight: 700; color: var(--gold); line-height: 1; }
.acl { font-size: .7rem; color: rgba(255,255,255,.5); margin-top: .2rem; }
.about-text h2 { margin-bottom: .5rem; }
.about-text p  { line-height: 1.9; margin-bottom: 1.1rem; }
.pills { display: flex; flex-wrap: wrap; gap: .55rem; margin: 1.75rem 0 2.25rem; }
.pill {
  display: inline-flex;
  align-items: center;
  gap: .35rem;
  padding: .4rem .9rem;
  background: var(--gold-f);
  border: 1px solid rgba(190,175,135,.35);
  font-size: .78rem;
  font-weight: 600;
  color: var(--dark);
  border-radius: 100px;
}
.pill::before { content: '✓'; color: var(--gold-dk); font-weight: 700; }
.about-btns { display: flex; gap: .85rem; flex-wrap: wrap; }

/* ============ AREAS ============ */
.areas-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1px;
  background: rgba(190,175,135,.14);
  margin-top: 3rem;
}
.area { background: rgba(255,255,255,.04); padding: 2rem 1.5rem; transition: background var(--t); }
.area:hover { background: rgba(190,175,135,.1); }
.ae { font-size: 1.6rem; margin-bottom: .8rem; display: block; }
.an { font-family: var(--serif); font-size: 1.05rem; font-weight: 600; color: var(--white); margin-bottom: .3rem; }
.as { font-size: .78rem; color: rgba(255,255,255,.42); line-height: 1.5; }

/* ============ REVIEWS ============ */
.rev-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 2rem;
  margin-bottom: 3rem;
}
.g-badge {
  display: flex;
  align-items: center;
  gap: 1.1rem;
  background: var(--white);
  border: 1px solid rgba(0,0,0,.08);
  box-shadow: 0 4px 18px rgba(0,0,0,.06);
  padding: 1.25rem 1.6rem;
  flex-shrink: 0;
}
.g-score { font-family: var(--serif); font-size: 2.4rem; font-weight: 700; color: var(--dark); line-height: 1; }
.g-stars { display: flex; gap: 2px; margin: 3px 0 2px; }
.gstar   { width: 17px; height: 17px; fill: #FBBC04; }
.g-cnt  { font-size: .76rem; color: var(--gray); }
.g-link { font-size: .76rem; color: #4285F4; font-weight: 600; text-decoration: underline; }
.g-logo { width: 30px; height: 30px; }
.rev-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.75rem; }
.rev-card {
  background: var(--white);
  border: 1px solid rgba(0,0,0,.07);
  box-shadow: 0 2px 10px rgba(0,0,0,.04);
  padding: 2rem;
  display: flex;
  flex-direction: column;
  position: relative;
  overflow: hidden;
  transition: all var(--t);
}
.rev-card:hover { transform: translateY(-4px); box-shadow: 0 12px 35px rgba(0,0,0,.09); }
.rev-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, #4285F4, #EA4335, #FBBC04, #34A853);
}
.rev-top { display: flex; align-items: center; gap: .8rem; margin-bottom: 1.1rem; }
.rev-av {
  width: 44px; height: 44px;
  border-radius: 50%;
  background: var(--gold-f);
  display: flex; align-items: center; justify-content: center;
  font-family: var(--serif);
  font-size: 1.05rem;
  font-weight: 700;
  color: var(--gold-dk);
  flex-shrink: 0;
}
.rev-nm { font-weight: 700; font-size: .9rem; color: var(--dark); }
.rev-dt { font-size: .75rem; color: var(--gray); margin-top: 1px; }
.rev-stars { display: flex; align-items: center; gap: .45rem; margin-bottom: .9rem; }
.rstar  { color: #FBBC04; font-size: .85rem; }
.rev-tag {
  font-size: .68rem; font-weight: 700; letter-spacing: .1em;
  text-transform: uppercase; color: #4285F4;
  background: rgba(66,133,244,.08);
  padding: .2rem .55rem; border-radius: 100px;
}
.rev-txt { font-size: .9rem; color: var(--mid); line-height: 1.85; flex: 1; font-style: italic; }
.rev-gl { display: flex; align-items: center; gap: .4rem; margin-top: 1.35rem; }
.rev-gl span { font-size: .7rem; color: var(--gray); }
.rev-cta {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1.1rem;
  margin-top: 2.75rem;
  flex-wrap: wrap;
}
.g-btn {
  display: inline-flex;
  align-items: center;
  gap: .55rem;
  padding: .75rem 1.6rem;
  border: 2px solid rgba(0,0,0,.12);
  font-size: .78rem; font-weight: 700;
  letter-spacing: .06em; text-transform: uppercase;
  color: var(--dark);
  transition: all var(--t);
  border-radius: 3px;
}
.g-btn:hover { border-color: #4285F4; color: #4285F4; transform: translateY(-2px); }

/* ============ CTA BAND ============ */
#jh-cta { padding: 5rem 0; background: var(--gold); }
.cta-inner {
  max-width: var(--max);
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 2rem;
  flex-wrap: wrap;
}
.cta-inner h2 { color: var(--dark); max-width: 540px; }
.cta-inner p  { color: rgba(28,28,28,.68); margin-top: .4rem; }
.cta-btns { display: flex; gap: .85rem; flex-wrap: wrap; flex-shrink: 0; }

/* ============ FAQ ============ */
.faq-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0 4rem;
  max-width: 980px;
  margin: 3rem auto 0;
}
.faq-item { border-bottom: 1px solid rgba(0,0,0,.08); }
.faq-q {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.25rem 0;
  background: none;
  border: none;
  cursor: pointer;
  text-align: left;
  font-family: var(--serif);
  font-size: 1rem;
  font-weight: 600;
  color: var(--dark);
  gap: 1rem;
}
.faq-q:hover { color: var(--gold-dk); }
.faq-ico {
  width: 24px; height: 24px;
  border-radius: 50%;
  background: var(--gold-f);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
  color: var(--gold-dk);
  flex-shrink: 0;
  transition: all var(--t);
}
.faq-a { max-height: 0; overflow: hidden; transition: max-height .4s ease; }
.faq-ai { padding: 0 0 1.25rem; font-size: .92rem; color: var(--mid); line-height: 1.85; }
.faq-item.open .faq-a   { max-height: 300px; }
.faq-item.open .faq-ico { transform: rotate(45deg); background: var(--gold); color: var(--white); }

/* ============ CONTACT ============ */
.contact-grid { display: grid; grid-template-columns: 1fr 1.3fr; gap: 5rem; align-items: start; }
.contact-left h2 { margin-bottom: .5rem; }
.cd-list { margin: 2.25rem 0; display: flex; flex-direction: column; gap: 1.1rem; }
.cd-item {
  display: flex;
  align-items: center;
  gap: .9rem;
  padding: 1.15rem 1.35rem;
  border: 1px solid rgba(190,175,135,.28);
  background: var(--light);
  transition: all var(--t);
}
a.cd-item:hover { border-color: var(--gold); background: var(--gold-f); transform: translateX(4px); }
.cd-ico {
  width: 42px; height: 42px;
  border-radius: 50%;
  background: var(--gold);
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
}
.cd-ico svg { width: 18px; height: 18px; stroke: var(--dark); }
.cd-lbl { font-size: .68rem; font-weight: 700; letter-spacing: .1em; text-transform: uppercase; color: var(--gray); }
.cd-val { font-size: 1rem; font-weight: 700; color: var(--dark); margin-top: 2px; }
.cd-hin { font-size: .76rem; color: var(--gray); margin-top: 1px; }
.cf-wrap { background: var(--light); padding: 2.75rem; }
.cf-wrap h3 { font-size: 1.3rem; color: var(--dark); margin-bottom: 1.75rem; }
.fg { margin-bottom: 1.3rem; }
.fl { display: block; font-size: .73rem; font-weight: 700; text-transform: uppercase; letter-spacing: .09em; color: var(--mid); margin-bottom: .45rem; }
.fi, .fs, .ft {
  width: 100%;
  padding: .85rem 1rem;
  border: 1px solid rgba(0,0,0,.12);
  background: var(--white);
  font-family: var(--sans);
  font-size: .93rem;
  color: var(--dark);
  outline: none;
  transition: border-color var(--t);
  border-radius: 3px;
}
.fi:focus, .fs:focus, .ft:focus { border-color: var(--gold); }
.ft { resize: vertical; min-height: 110px; }
.fr { display: grid; grid-template-columns: 1fr 1fr; gap: .9rem; }

/* ============ FOOTER ============ */
#jh-footer { background: #0C0C0C; padding: 2.75rem 0 2rem; }
.foot-top {
  max-width: var(--max);
  margin: 0 auto;
  padding: 0 2rem 2rem;
  border-bottom: 1px solid rgba(190,175,135,.12);
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 2rem;
  flex-wrap: wrap;
}
.foot-name { font-family: var(--serif); font-size: 1.3rem; color: var(--white); }
.foot-sub  { font-size: .68rem; font-weight: 700; letter-spacing: .17em; text-transform: uppercase; color: var(--gold); margin-top: 3px; }
.foot-links { display: flex; gap: 1.5rem; list-style: none; flex-wrap: wrap; }
.foot-links a { font-size: .8rem; color: rgba(255,255,255,.38); transition: color var(--t); }
.foot-links a:hover { color: var(--gold); }
.foot-bot {
  max-width: var(--max);
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: .6rem;
}
.foot-copy { font-size: .76rem; color: rgba(255,255,255,.28); }
.foot-copy a { color: var(--gold); }
.foot-disc { font-size: .7rem; color: rgba(255,255,255,.18); text-align: right; max-width: 400px; line-height: 1.6; }

/* ============ RESPONSIVE ============ */
@media (max-width: 1024px) {
  .svc-grid   { grid-template-columns: repeat(2, 1fr); }
  .areas-grid { grid-template-columns: repeat(2, 1fr); }
  .rev-grid   { grid-template-columns: 1fr 1fr; }
  .about-grid { gap: 3rem; }
  .about-chip { display: none; }
  .faq-grid   { grid-template-columns: 1fr; }
  .si         { grid-template-columns: repeat(2, 1fr); }
  .stat:nth-child(2) { border-right: none; }
  .stat:nth-child(3) { border-right: 1px solid rgba(28,28,28,.14); }
}

@media (max-width: 768px) {
  .section { padding: 4rem 0; }
  .nl {
    display: none;
    position: fixed;
    top: 66px; left: 0; right: 0;
    background: rgba(17,17,17,.98);
    flex-direction: column;
    align-items: flex-start;
    padding: 1.5rem 2rem;
    gap: 1.1rem;
    border-top: 1px solid rgba(190,175,135,.15);
  }
  .nl.open   { display: flex; }
  .nav-tog   { display: flex; }
  #jh-hero   { grid-template-columns: 1fr; min-height: auto; }
  .h-left    { padding: 3rem 1.5rem; }
  .h-right   { height: 380px; }
  .h-contact { flex-direction: column; gap: .85rem; }
  .hc-div    { display: none; }
  .about-grid    { grid-template-columns: 1fr; gap: 2.5rem; }
  .aph           { aspect-ratio: 3/2; }
  .svc-grid      { grid-template-columns: 1fr; }
  .rev-grid      { grid-template-columns: 1fr; }
  .rev-header    { flex-direction: column; }
  .contact-grid  { grid-template-columns: 1fr; gap: 2.5rem; }
  .fr            { grid-template-columns: 1fr; }
  .cta-inner     { flex-direction: column; text-align: center; }
  .cta-btns      { justify-content: center; }
  .foot-top      { flex-direction: column; text-align: center; }
  .foot-links    { justify-content: center; }
  .foot-bot      { flex-direction: column; align-items: center; text-align: center; }
  .foot-disc     { text-align: center; }
}

@media (max-width: 480px) {
  .wrap { padding: 0 1.25rem; }
  .ni   { padding: .85rem 1.25rem; }
  .h-left { padding: 2.5rem 1.25rem; }
  .cf-wrap { padding: 1.75rem 1.25rem; }
  .areas-grid { grid-template-columns: 1fr; }
  .si { grid-template-columns: repeat(2, 1fr); }
}

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { transition: none !important; animation: none !important; }
}
