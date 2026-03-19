<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Skincare Routine — 45F Asian Skin</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #F8F4EF;
    --warm-white: #FDFAF7;
    --blush: #E8D5C4;
    --rose: #C4856A;
    --rose-deep: #9E5E47;
    --plum: #3D2B35;
    --plum-mid: #6B4A5A;
    --plum-light: #9B7A8A;
    --gold: #B8965A;
    --gold-light: #D4B07A;
    --night-bg: #1A1118;
    --night-surface: #241A20;
    --night-border: #3A2830;
    --text-dark: #2A1E24;
    --text-mid: #5A4450;
    --text-light: #8A7080;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--text-dark);
    min-height: 100vh;
    padding: 0;
  }

  /* Header */
  .header {
    background: var(--plum);
    padding: 56px 48px 48px;
    position: relative;
    overflow: hidden;
  }
  .header::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 320px; height: 320px;
    border-radius: 50%;
    border: 1px solid rgba(255,255,255,0.06);
  }
  .header::after {
    content: '';
    position: absolute;
    bottom: -40px; left: -40px;
    width: 200px; height: 200px;
    border-radius: 50%;
    border: 1px solid rgba(255,255,255,0.04);
  }
  .header-eyebrow {
    font-family: 'DM Sans', sans-serif;
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold-light);
    margin-bottom: 14px;
  }
  .header-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 42px;
    font-weight: 300;
    color: #F8F2EE;
    line-height: 1.15;
    margin-bottom: 8px;
  }
  .header-title em {
    font-style: italic;
    color: var(--gold-light);
  }
  .header-sub {
    font-size: 13px;
    color: var(--plum-light);
    font-weight: 300;
    margin-top: 12px;
    letter-spacing: 0.02em;
  }
  .header-pills {
    display: flex;
    gap: 8px;
    margin-top: 24px;
    flex-wrap: wrap;
  }
  .header-pill {
    padding: 5px 14px;
    border-radius: 20px;
    border: 1px solid rgba(255,255,255,0.12);
    font-size: 11px;
    font-weight: 400;
    color: rgba(255,255,255,0.55);
    letter-spacing: 0.04em;
  }

  /* Tab nav */
  .tab-nav {
    background: var(--warm-white);
    border-bottom: 1px solid var(--blush);
    display: flex;
    padding: 0 48px;
    position: sticky;
    top: 0;
    z-index: 10;
  }
  .tab-btn {
    padding: 18px 0;
    margin-right: 36px;
    font-size: 13px;
    font-weight: 400;
    color: var(--text-light);
    border: none;
    background: none;
    cursor: pointer;
    border-bottom: 2px solid transparent;
    transition: all .2s;
    letter-spacing: 0.02em;
  }
  .tab-btn.active {
    color: var(--rose-deep);
    border-bottom-color: var(--rose);
    font-weight: 500;
  }

  /* Content */
  .content { padding: 0 48px 64px; background: var(--warm-white); }
  .panel { display: none; }
  .panel.active { display: block; }

  /* Routine steps */
  .session-label {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 40px 0 24px;
  }
  .session-icon {
    width: 36px; height: 36px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 14px;
    flex-shrink: 0;
  }
  .session-icon.am { background: #FDF3E8; color: #B8965A; border: 1px solid #E8D5B0; }
  .session-icon.pm { background: #1A1118; color: #9B7A8A; border: 1px solid #3A2830; }
  .session-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 26px;
    font-weight: 400;
    color: var(--text-dark);
  }
  .session-tagline {
    font-size: 12px;
    color: var(--text-light);
    font-weight: 300;
    margin-top: 1px;
    letter-spacing: 0.04em;
  }

  .steps { display: flex; flex-direction: column; gap: 0; }
  .step {
    display: grid;
    grid-template-columns: 56px 1fr;
    gap: 0;
    border-top: 1px solid #EDE5DE;
    padding: 22px 0;
    transition: background .15s;
  }
  .step:last-child { border-bottom: 1px solid #EDE5DE; }
  .step-left {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 3px;
  }
  .step-num {
    width: 28px; height: 28px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 11px;
    font-weight: 500;
    flex-shrink: 0;
  }
  .step-num.am { background: var(--cream); color: var(--gold); border: 1px solid var(--blush); }
  .step-num.pm { background: var(--night-surface); color: var(--plum-light); border: 1px solid var(--night-border); }
  .step-line {
    width: 1px;
    flex: 1;
    margin-top: 8px;
    min-height: 24px;
  }
  .step-line.am { background: linear-gradient(to bottom, #E8D5C4, transparent); }
  .step-line.pm { background: linear-gradient(to bottom, #3A2830, transparent); }
  .step-right { padding-left: 20px; }
  .step-product {
    font-size: 14px;
    font-weight: 500;
    color: var(--text-dark);
    margin-bottom: 4px;
    letter-spacing: 0.01em;
  }
  .step-brand {
    font-size: 10px;
    font-weight: 400;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--text-light);
    margin-bottom: 6px;
  }
  .step-desc {
    font-size: 12.5px;
    color: var(--text-mid);
    line-height: 1.65;
    font-weight: 300;
  }
  .step-tags { margin-top: 8px; display: flex; gap: 5px; flex-wrap: wrap; }
  .stag {
    font-size: 10px;
    font-weight: 500;
    padding: 2px 8px;
    border-radius: 20px;
    letter-spacing: 0.03em;
  }
  .stag.green { background: #EAF3DE; color: #3B6D11; }
  .stag.blue { background: #E6F1FB; color: #185FA5; }
  .stag.amber { background: #FDF3E8; color: #854F0B; }
  .stag.red { background: #FCEBEB; color: #A32D2D; }
  .stag.plum { background: #F0EAF0; color: #6B4A5A; }
  .stag.device { background: var(--plum); color: var(--gold-light); }

  /* Booster callout */
  .booster-callout {
    margin: 6px 0 0;
    padding: 10px 14px;
    background: var(--plum);
    border-radius: 8px;
    font-size: 12px;
    color: rgba(255,255,255,0.65);
    line-height: 1.55;
  }
  .booster-callout strong { color: var(--gold-light); font-weight: 500; }

  /* Wait step */
  .step.wait .step-product { color: var(--rose-deep); font-style: italic; }

  /* Alert box */
  .alert {
    margin: 8px 0 0;
    padding: 10px 14px;
    border-radius: 8px;
    font-size: 12px;
    line-height: 1.55;
  }
  .alert.warn { background: #FDF3E8; color: #854F0B; border-left: 3px solid var(--gold); }
  .alert.critical { background: #FCEBEB; color: #A32D2D; border-left: 3px solid #E24B4A; }
  .alert.info { background: #E6F1FB; color: #185FA5; border-left: 3px solid #378ADD; }

  /* Divider between AM and PM in routine tab */
  .routine-divider {
    margin: 8px 0 0;
    height: 1px;
    background: linear-gradient(to right, var(--blush), transparent);
  }

  /* Ingredients panel */
  .ing-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; padding-top: 32px; }
  .ing-card {
    background: var(--cream);
    border-radius: 12px;
    border: 1px solid var(--blush);
    padding: 20px;
  }
  .ing-card-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 18px;
    font-weight: 400;
    color: var(--text-dark);
    margin-bottom: 4px;
  }
  .ing-card-brand {
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--text-light);
    margin-bottom: 14px;
    padding-bottom: 12px;
    border-bottom: 1px solid var(--blush);
  }
  .ing-item {
    display: flex;
    gap: 8px;
    align-items: flex-start;
    padding: 6px 0;
    border-bottom: 1px solid rgba(0,0,0,0.04);
  }
  .ing-item:last-child { border-bottom: none; }
  .ing-dot-sm { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; margin-top: 5px; }
  .ing-item-name { font-size: 12px; font-weight: 500; color: var(--text-dark); }
  .ing-item-role { font-size: 11px; color: var(--text-light); font-weight: 300; }

  /* Notes panel */
  .notes-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; padding-top: 32px; }
  .note-card {
    border-radius: 12px;
    padding: 22px;
    border: 1px solid transparent;
  }
  .note-card.green { background: #EAF3DE; border-color: #C0DD97; }
  .note-card.amber { background: #FDF3E8; border-color: #E8D5B0; }
  .note-card.red { background: #FCEBEB; border-color: #F7C1C1; }
  .note-card.plum { background: #F8F0F5; border-color: #DCC8D4; }
  .note-card.blue { background: #E6F1FB; border-color: #B5D4F4; }
  .note-title {
    font-size: 12px;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-bottom: 10px;
  }
  .note-card.green .note-title { color: #3B6D11; }
  .note-card.amber .note-title { color: #854F0B; }
  .note-card.red .note-title { color: #A32D2D; }
  .note-card.plum .note-title { color: #6B4A5A; }
  .note-card.blue .note-title { color: #185FA5; }
  .note-body {
    font-size: 13px;
    line-height: 1.65;
    font-weight: 300;
  }
  .note-card.green .note-body { color: #3B6D11; }
  .note-card.amber .note-body { color: #854F0B; }
  .note-card.red .note-body { color: #A32D2D; }
  .note-card.plum .note-body { color: #6B4A5A; }
  .note-card.blue .note-body { color: #185FA5; }
  .note-card.full { grid-column: 1 / -1; }

  /* Score summary */
  .score-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; padding-top: 32px; margin-bottom: 24px; }
  .score-card {
    background: var(--cream);
    border: 1px solid var(--blush);
    border-radius: 12px;
    padding: 18px;
    text-align: center;
  }
  .score-val {
    font-family: 'Cormorant Garamond', serif;
    font-size: 36px;
    font-weight: 300;
    color: var(--plum);
    line-height: 1;
  }
  .score-val span { font-size: 16px; color: var(--text-light); }
  .score-label { font-size: 11px; color: var(--text-light); margin-top: 6px; letter-spacing: 0.04em; }
  .score-bar { height: 3px; background: var(--blush); border-radius: 2px; margin-top: 10px; overflow: hidden; }
  .score-fill { height: 100%; border-radius: 2px; background: var(--rose); }

  @media (max-width: 680px) {
    .header { padding: 40px 24px 36px; }
    .header-title { font-size: 32px; }
    .tab-nav { padding: 0 24px; overflow-x: auto; }
    .content { padding: 0 24px 48px; }
    .ing-grid, .notes-grid, .score-row { grid-template-columns: 1fr; }
    .score-row { grid-template-columns: 1fr 1fr; }
    .note-card.full { grid-column: 1; }
  }

  /* Intro sequence slide up */
  @keyframes fadeUp { from { opacity:0; transform:translateY(12px); } to { opacity:1; transform:translateY(0); } }
  .header-eyebrow { animation: fadeUp .5s ease both; }
  .header-title { animation: fadeUp .5s .1s ease both; }
  .header-sub { animation: fadeUp .5s .2s ease both; }
  .header-pills { animation: fadeUp .5s .3s ease both; }
</style>
</head>
<body>

<div class="header">
  <div class="header-eyebrow">Personalised Skincare Protocol</div>
  <div class="header-title">45F <em>Asian Skin</em><br>Routine</div>
  <div class="header-sub">Tretinoin · Brightening · Anti-aging · Barrier repair</div>
  <div class="header-pills">
    <div class="header-pill">PIH / Melasma</div>
    <div class="header-pill">Collagen support</div>
    <div class="header-pill">Barrier integrity</div>
    <div class="header-pill">Electroporation AM</div>
  </div>
</div>

<nav class="tab-nav">
  <button class="tab-btn active" onclick="show('routine',this)">Full routine</button>
  <button class="tab-btn" onclick="show('ingredients',this)">Key ingredients</button>
  <button class="tab-btn" onclick="show('notes',this)">Notes & warnings</button>
</nav>

<div class="content">

  <!-- ROUTINE TAB -->
  <div class="panel active" id="routine">

    <!-- AM -->
    <div class="session-label">
      <div class="session-icon am">☀</div>
      <div>
        <div class="session-name">Morning</div>
        <div class="session-tagline">Brighten · Protect · Electroporate</div>
      </div>
    </div>

    <div class="steps">
      <div class="step">
        <div class="step-left">
          <div class="step-num am">1</div>
          <div class="step-line am"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Cleanser</div>
          <div class="step-product">Gentle low-pH cleanser</div>
          <div class="step-desc">Non-foaming, fragrance-free. Sets the correct pH baseline before actives. Avoid anything stripping — tretinoin keeps skin sensitised overnight.</div>
          <div class="step-tags"><span class="stag blue">ph balanced</span></div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num am">2</div>
          <div class="step-line am"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Missha</div>
          <div class="step-product">Time Revolution First Essence 5X</div>
          <div class="step-desc">Applied to freshly cleansed skin while still slightly damp. Watery texture absorbs immediately. Bifida ferment, ceramide NP and adenosine prime skin and restore microbiome balance.</div>
          <div class="step-tags"><span class="stag green">bifida ferment</span><span class="stag green">ceramide NP</span><span class="stag green">fragrance-free</span></div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num am">3</div>
          <div class="step-line am"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">KisoCare</div>
          <div class="step-product">Azelaic Acid 15% · Niacinamide · Vitamin C</div>
          <div class="step-desc">Your AM active powerhouse. Potassium azeloyl diglycinate (azelaic), sodium ascorbyl phosphate (stable vitamin C), and niacinamide in one step. Triple-pathway pigmentation suppression — the gold standard for Asian skin.</div>
          <div class="step-tags"><span class="stag green">azelaic</span><span class="stag green">vitamin C</span><span class="stag green">niacinamide</span><span class="stag green">4× HA</span></div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num am">4</div>
          <div class="step-line am"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Medicube</div>
          <div class="step-product">Collagen Jelly Cream + Booster-H</div>
          <div class="step-desc">Apply jelly cream, then use Booster-H immediately for ~5 min. The gel texture is purpose-built for electroporation. Collagen, elastin, squalane and adenosine are driven 490% deeper than hand application. Start at level 1 and build gradually.</div>
          <div class="step-tags"><span class="stag device">booster-H</span><span class="stag plum">electroporation</span><span class="stag green">collagen</span><span class="stag amber">patch test</span></div>
          <div class="booster-callout"><strong>Device rule:</strong> Booster-H belongs exclusively in AM. Never use with tretinoin. The 490% penetration increase would drive retinoic acid dangerously deep, causing severe irritation and PIH risk.</div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num am">5</div>
          <div class="step-line am"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Numbuzin</div>
          <div class="step-product">No.9 NAD+ Bio Lifting-sil Essence</div>
          <div class="step-desc">50+ peptide types including copper tripeptide-1, palmitoyl tripeptide-5, and acetyl hexapeptide-8. NAD+ precursors, glutathione, astaxanthin. Richer texture seals the active layer beneath. Fragrance-free — safe under SPF.</div>
          <div class="step-tags"><span class="stag plum">50+ peptides</span><span class="stag green">NAD+</span><span class="stag green">antioxidants</span><span class="stag green">fragrance-free</span></div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num am">6</div>
          <div class="step-line am"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">CeraVe</div>
          <div class="step-product">Moisturizing Cream</div>
          <div class="step-desc">Thin morning layer. Ceramides 1, 3 and 6-II rebuild the barrier. Petrolatum seals all active layers before SPF. MVE technology delivers ceramides gradually. Bridges overnight barrier repair into daytime protection.</div>
          <div class="step-tags"><span class="stag green">ceramides 1,3,6-II</span><span class="stag blue">barrier seal</span></div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num am">7</div>
        </div>
        <div class="step-right">
          <div class="step-brand">Sunscreen</div>
          <div class="step-product">Broad-spectrum SPF 50+</div>
          <div class="step-desc">The single most important step in the entire routine. Every brightening active is undermined by unprotected UV. Apply generously and reapply every 2 hours outdoors. Mineral (zinc oxide) preferred on sensitised skin.</div>
          <div class="step-tags"><span class="stag red">non-negotiable</span><span class="stag amber">reapply 2-hourly</span></div>
        </div>
      </div>
    </div>

    <div class="routine-divider"></div>

    <!-- PM -->
    <div class="session-label">
      <div class="session-icon pm">◗</div>
      <div>
        <div class="session-name">Evening</div>
        <div class="session-tagline">Renew · Repair · Seal</div>
      </div>
    </div>

    <div class="steps">
      <div class="step">
        <div class="step-left">
          <div class="step-num pm">1</div>
          <div class="step-line pm"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Cleanse</div>
          <div class="step-product">Double cleanse</div>
          <div class="step-desc">Oil or balm cleanser first to dissolve SPF and makeup. Follow with gentle cleanser. Residual SPF blocks tretinoin absorption — thorough cleansing is non-negotiable.</div>
          <div class="step-tags"><span class="stag red">do not skip oil step</span></div>
        </div>
      </div>

      <div class="step wait">
        <div class="step-left">
          <div class="step-num pm">2</div>
          <div class="step-line pm"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Wait</div>
          <div class="step-product">10–15 minutes — skin must be completely dry</div>
          <div class="step-desc">Tretinoin applied to damp skin absorbs dramatically faster, greatly increasing irritation and PIH risk. This wait is one of the highest-impact steps in the routine.</div>
          <div class="step-tags"><span class="stag red">mandatory</span></div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num pm">3</div>
          <div class="step-line pm"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Missha</div>
          <div class="step-product">Time Revolution First Essence Enriched</div>
          <div class="step-desc">Richer, thicker texture than the 5X — ideal for mature and dry skin at night. Beta glucan, Extreme Biome™ with 10 probiotics, bifida ferment and adenosine prep skin for tretinoin while starting overnight barrier restoration. Fragrance-free.</div>
          <div class="step-tags"><span class="stag plum">beta glucan</span><span class="stag plum">10 probiotics</span><span class="stag green">fragrance-free</span><span class="stag blue">PM only</span></div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num pm">4</div>
          <div class="step-line pm"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">CeraVe</div>
          <div class="step-product">Moisturizing Cream — buffer layer</div>
          <div class="step-desc">Thin layer before tretinoin. The sandwich method — slows absorption slightly to reduce flaking and irritation without meaningfully compromising tretinoin efficacy. Optional once skin is fully adapted.</div>
          <div class="step-tags"><span class="stag blue">sandwich buffer</span></div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num pm">5</div>
          <div class="step-line pm"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Rx</div>
          <div class="step-product">Tretinoin</div>
          <div class="step-desc">Pea-sized amount across the whole face. Avoid the eye area and lips. The core of this entire routine — drives collagen synthesis, accelerates cell turnover, fades pigmentation. Everything else exists to support this step.</div>
          <div class="step-tags"><span class="stag red">key active</span><span class="stag amber">avoid eye area</span><span class="stag amber">pea-sized only</span></div>
          <div class="alert warn">Build slowly if adjusting frequency. Use 3×/week before going nightly. Purging can last 6–8 weeks — stay the course.</div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num pm">6</div>
          <div class="step-line pm"></div>
        </div>
        <div class="step-right">
          <div class="step-brand">Missha</div>
          <div class="step-product">Time Revolution Night Repair Ampoule 5X</div>
          <div class="step-desc">77.2% bifida ferment lysate as the base — the highest concentration in any product in this routine. Squalane, panthenol, sodium hyaluronate, niacinamide and a 10-probiotic complex work overnight to repair and replenish.</div>
          <div class="step-tags"><span class="stag plum">77% bifida ferment</span><span class="stag green">squalane</span><span class="stag green">panthenol</span></div>
          <div class="alert warn">Contains bergamot and geranium oil (low concentration, near bottom of list). Patch test for 7 days on inner arm before full face use. Discontinue if any irritation occurs.</div>
        </div>
      </div>

      <div class="step">
        <div class="step-left">
          <div class="step-num pm">7</div>
        </div>
        <div class="step-right">
          <div class="step-brand">CeraVe</div>
          <div class="step-product">Moisturizing Cream — seal layer</div>
          <div class="step-desc">Generous final layer. Petrolatum creates an occlusive seal locking in all active layers. Ceramides 1, 3 and 6-II restore barrier lipids depleted by tretinoin overnight. MVE technology delivers ceramides continuously as you sleep.</div>
          <div class="step-tags"><span class="stag blue">final seal</span><span class="stag green">ceramides</span><span class="stag blue">MVE delivery</span></div>
        </div>
      </div>
    </div>
  </div>

  <!-- INGREDIENTS TAB -->
  <div class="panel" id="ingredients">
    <div class="score-row">
      <div class="score-card">
        <div class="score-val">9.5<span>/10</span></div>
        <div class="score-label">PIH coverage</div>
        <div class="score-bar"><div class="score-fill" style="width:95%"></div></div>
      </div>
      <div class="score-card">
        <div class="score-val">9<span>/10</span></div>
        <div class="score-label">Anti-aging</div>
        <div class="score-bar"><div class="score-fill" style="width:90%"></div></div>
      </div>
      <div class="score-card">
        <div class="score-val">9<span>/10</span></div>
        <div class="score-label">Barrier repair</div>
        <div class="score-bar"><div class="score-fill" style="width:90%"></div></div>
      </div>
      <div class="score-card">
        <div class="score-val">Low</div>
        <div class="score-label">Irritation risk</div>
        <div class="score-bar"><div class="score-fill" style="width:18%;background:#1D9E75"></div></div>
      </div>
    </div>

    <div class="ing-grid">
      <div class="ing-card">
        <div class="ing-card-title">Pigmentation actives</div>
        <div class="ing-card-brand">Triple-pathway approach for Asian skin</div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#1D9E75"></div><div><div class="ing-item-name">Tretinoin (PM)</div><div class="ing-item-role">Cell turnover, fades existing PIH</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#1D9E75"></div><div><div class="ing-item-name">Azelaic acid derivative (AM)</div><div class="ing-item-role">Inhibits tyrosinase, anti-inflammatory</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#1D9E75"></div><div><div class="ing-item-name">Sodium ascorbyl phosphate (AM)</div><div class="ing-item-role">Stable vitamin C, melanin suppression</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#1D9E75"></div><div><div class="ing-item-name">Niacinamide (AM + PM)</div><div class="ing-item-role">Blocks melanosome transfer, brightens</div></div></div>
      </div>

      <div class="ing-card">
        <div class="ing-card-title">Collagen & anti-aging</div>
        <div class="ing-card-brand">Dual-pathway collagen stimulation</div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#7F77DD"></div><div><div class="ing-item-name">Tretinoin (PM)</div><div class="ing-item-role">Retinoic acid receptor activation</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#7F77DD"></div><div><div class="ing-item-name">50+ peptides — No.9 (AM)</div><div class="ing-item-role">Signal peptides incl. copper tripeptide-1</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#7F77DD"></div><div><div class="ing-item-name">Hydrolyzed collagen & elastin (AM)</div><div class="ing-item-role">Surface film, long-term signalling</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#7F77DD"></div><div><div class="ing-item-name">Adenosine (AM + PM)</div><div class="ing-item-role">Anti-wrinkle, supports elastin</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#7F77DD"></div><div><div class="ing-item-name">NAD+ precursors (AM)</div><div class="ing-item-role">Cellular energy & DNA repair</div></div></div>
      </div>

      <div class="ing-card">
        <div class="ing-card-title">Barrier & hydration</div>
        <div class="ing-card-brand">Humectant → emollient → occlusive structure</div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#378ADD"></div><div><div class="ing-item-name">Ceramides 1, 3, 6-II (AM + PM)</div><div class="ing-item-role">Barrier lipid replacement — CeraVe</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#378ADD"></div><div><div class="ing-item-name">4× hyaluronic acid (AM)</div><div class="ing-item-role">Multi-weight humectant — KisoCare AZ</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#378ADD"></div><div><div class="ing-item-name">Beta glucan (PM)</div><div class="ing-item-role">Deep structural hydration — Enriched</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#378ADD"></div><div><div class="ing-item-name">Squalane (PM)</div><div class="ing-item-role">Emollient — Night Repair Ampoule</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#378ADD"></div><div><div class="ing-item-name">Petrolatum (AM + PM)</div><div class="ing-item-role">Occlusive seal — CeraVe</div></div></div>
      </div>

      <div class="ing-card">
        <div class="ing-card-title">Probiotic & antioxidant</div>
        <div class="ing-card-brand">Microbiome restoration + oxidative defence</div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#9B7A8A"></div><div><div class="ing-item-name">Bifida ferment lysate (AM + PM)</div><div class="ing-item-role">Microbiome repair, radiance</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#9B7A8A"></div><div><div class="ing-item-name">10-probiotic Extreme Biome™ (PM)</div><div class="ing-item-role">Comprehensive microbiome support</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#9B7A8A"></div><div><div class="ing-item-name">Glutathione (AM)</div><div class="ing-item-role">Master antioxidant, brightening</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#9B7A8A"></div><div><div class="ing-item-name">Astaxanthin (AM)</div><div class="ing-item-role">6000× stronger than vitamin C</div></div></div>
        <div class="ing-item"><div class="ing-dot-sm" style="background:#9B7A8A"></div><div><div class="ing-item-name">5 purple extracts (PM)</div><div class="ing-item-role">Beet, blueberry, carrot, cabbage, eggplant</div></div></div>
      </div>
    </div>
  </div>

  <!-- NOTES TAB -->
  <div class="panel" id="notes">
    <div class="notes-grid" style="padding-top:32px">

      <div class="note-card green full">
        <div class="note-title">Overall assessment</div>
        <div class="note-body">This is one of the most complete non-prescription routines possible for 45-year-old Asian skin. Every major concern — PIH, melasma, collagen loss, barrier repair, hydration, and microbiome balance — is addressed with clinically meaningful ingredients and genuine synergies between products. The addition of the Booster-H amplifies AM actives significantly without interfering with the PM tretinoin protocol.</div>
      </div>

      <div class="note-card amber">
        <div class="note-title">Introduction schedule</div>
        <div class="note-body">Do not introduce everything at once. Week 1–2: KisoCare AZ only in AM. Week 3–4: Add First Essences. Week 5–6: Add No.9 Essence. Week 7: Add Collagen Jelly + Booster-H at level 1. Week 9: Add Night Repair Ampoule after patch testing. Keep tretinoin as-is throughout.</div>
      </div>

      <div class="note-card red">
        <div class="note-title">Critical warnings</div>
        <div class="note-body">1. Never use the Booster-H on the same occasion as tretinoin. 2. Patch test the Night Repair Ampoule for 7 days — bergamot and geranium oil are present. 3. Do not use AHAs or BHAs — tretinoin provides all cell turnover needed. 4. Never apply tretinoin to damp skin.</div>
      </div>

      <div class="note-card plum">
        <div class="note-title">Asian skin specifics</div>
        <div class="note-body">Fitzpatrick III–V skin is highly prone to PIH from irritation itself. Ironically, rushing actives to fix pigmentation can worsen it. The slow introduction schedule is not optional — it is the strategy. Any redness, stinging or new dark spots are signals to pause and allow barrier recovery before continuing.</div>
      </div>

      <div class="note-card blue">
        <div class="note-title">On rushed days</div>
        <div class="note-body">AM non-negotiables: KisoCare AZ + SPF. PM non-negotiables: Tretinoin + CeraVe seal. Everything else enhances the routine but these four steps are the core that must never be skipped. Consistency over months matters more than perfection every day.</div>
      </div>

      <div class="note-card amber">
        <div class="note-title">Next upgrade</div>
        <div class="note-body">If stubborn melasma or PIH persists after 3 months: add tranexamic acid serum in AM between KisoCare AZ and the Jelly Cream. It targets melanin production via a fourth independent pathway not covered by anything currently in this routine. Also consider a dedicated peptide eye cream for the orbital area tretinoin cannot reach.</div>
      </div>

      <div class="note-card green full">
        <div class="note-title">The one thing that determines success</div>
        <div class="note-body">SPF compliance. Every brightening active in this routine is significantly undermined by unprotected UV exposure. Tretinoin, azelaic acid, vitamin C, niacinamide — none of them can outperform daily sun exposure. Broad-spectrum SPF 50+ applied generously every morning and reapplied every 2 hours outdoors is the foundation everything else builds on.</div>
      </div>

    </div>
  </div>

</div>

<script>
function show(id, el) {
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(t => t.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  el.classList.add('active');
}
</script>
</body>
</html>
