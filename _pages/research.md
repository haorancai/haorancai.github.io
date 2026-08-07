---
layout: page
permalink: /research/
title: Research
description: 
nav: true
nav_order: 1
---

<style>
/* ═══════════════════════════════════════════════════════════════
   Research Page – Custom Styles
   ═══════════════════════════════════════════════════════════════ */

/* ---------- Hero Section ---------- */
.research-hero {
  text-align: center;
  margin-bottom: 3rem;
  padding: 2rem 0;
}

.research-hero .lead-text {
  font-size: 1.15rem;
  line-height: 1.8;
  color: var(--global-text-color);
  max-width: 700px;
  margin: 0 auto;
  opacity: 0.85;
}

/* ---------- SVG Diagram ---------- */
.research-diagram-wrapper {
  display: flex;
  justify-content: center;
  margin: 2.5rem auto 3.5rem;
  max-width: 780px;
}

.research-diagram-wrapper svg {
  width: 100%;
  height: auto;
}

/* Animate the bridge arcs on load */
@keyframes drawArc {
  from { stroke-dashoffset: 600; }
  to   { stroke-dashoffset: 0; }
}

.bridge-arc {
  stroke-dasharray: 600;
  stroke-dashoffset: 600;
  animation: drawArc 1.6s ease-out forwards;
}

.bridge-arc-1 { animation-delay: 0.2s; }
.bridge-arc-2 { animation-delay: 0.6s; }
.bridge-arc-3 { animation-delay: 1.0s; }

/* Pulse the central node */
@keyframes pulse {
  0%, 100% { r: 32; opacity: 0.25; }
  50%      { r: 40; opacity: 0.12; }
}

.center-pulse {
  animation: pulse 3s ease-in-out infinite;
}

/* Fade-in for node groups */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(12px); }
  to   { opacity: 1; transform: translateY(0); }
}

.node-group {
  opacity: 0;
  animation: fadeUp 0.7s ease-out forwards;
}

.node-group:nth-child(1)  { animation-delay: 0.3s; }
.node-group:nth-child(2)  { animation-delay: 0.5s; }
.node-group:nth-child(3)  { animation-delay: 0.7s; }
.node-group:nth-child(4)  { animation-delay: 0.9s; }
.node-group:nth-child(5)  { animation-delay: 1.1s; }
.node-group:nth-child(6)  { animation-delay: 1.3s; }
.node-group:nth-child(7)  { animation-delay: 0.1s; }

/* ---------- Bridge Cards ---------- */
.bridge-section {
  margin: 3rem 0 2rem;
}

.bridge-section .section-label {
  font-size: 0.75rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--global-theme-color);
  margin-bottom: 0.3rem;
  font-weight: 600;
}

.bridge-section h3 {
  font-size: 1.35rem;
  margin-bottom: 1rem;
  font-weight: 600;
}

.bridge-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.bridge-card {
  position: relative;
  padding: 1.8rem;
  border-radius: 14px;
  border: 1px solid var(--global-divider-color);
  background: var(--global-card-bg-color);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  overflow: hidden;
}

.bridge-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  border-radius: 14px 14px 0 0;
}

.bridge-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 32px rgba(0,0,0,0.08);
}

html[data-theme="dark"] .bridge-card:hover {
  box-shadow: 0 12px 32px rgba(0,0,0,0.35);
}

.bridge-card .card-icon {
  font-size: 2rem;
  margin-bottom: 0.6rem;
  display: block;
}

.bridge-card h4 {
  font-size: 1.05rem;
  font-weight: 600;
  margin-bottom: 0.4rem;
}

.bridge-card p {
  font-size: 0.92rem;
  line-height: 1.65;
  color: var(--global-text-color-light);
  margin-bottom: 0;
}

/* Card accent colors — unified palette */
.bridge-card.accent-scale::before   { background: linear-gradient(90deg, #FED789, #023743); }
.bridge-card.accent-evo::before     { background: linear-gradient(90deg, #023743, #FED789); }
.bridge-card.accent-stat::before    { background: linear-gradient(90deg, #72874E, #476F84); }
.bridge-card.accent-mech::before    { background: linear-gradient(90deg, #476F84, #72874E); }
.bridge-card.accent-emp::before     { background: linear-gradient(90deg, #A4BED5, #453947); }
.bridge-card.accent-theo::before    { background: linear-gradient(90deg, #453947, #A4BED5); }

/* ---------- Dimensions Section ---------- */
.dimension-row {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  align-items: center;
  gap: 1rem;
  margin: 2rem 0;
  padding: 1.5rem 0;
  border-bottom: 1px solid var(--global-divider-color);
}

.dimension-row:last-child {
  border-bottom: none;
}

.dim-pole {
  padding: 1.2rem 1.5rem;
  border-radius: 12px;
  border: 1px solid var(--global-divider-color);
  background: var(--global-card-bg-color);
}

.dim-pole h4 {
  font-size: 1rem;
  font-weight: 600;
  margin-bottom: 0.3rem;
}

.dim-pole .subtitle {
  font-size: 0.82rem;
  color: var(--global-text-color-light);
  margin-bottom: 0;
}

.dim-bridge {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.3rem;
  min-width: 100px;
}

.dim-bridge .bridge-icon {
  font-size: 1.6rem;
  color: var(--global-theme-color);
}

.dim-bridge .bridge-label {
  font-size: 0.7rem;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--global-theme-color);
  font-weight: 600;
}

/* ---------- Approach Badges ---------- */
.approach-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-top: 0.6rem;
}

.approach-tag {
  display: inline-flex;
  align-items: center;
  gap: 0.3rem;
  padding: 0.25rem 0.7rem;
  border-radius: 20px;
  font-size: 0.78rem;
  font-weight: 500;
  border: 1px solid var(--global-divider-color);
  background: var(--global-bg-color);
  color: var(--global-text-color-light);
  transition: background 0.2s, color 0.2s;
}

.approach-tag:hover {
  background: var(--global-theme-color);
  color: var(--global-hover-text-color);
  border-color: var(--global-theme-color);
}

/* ---------- Responsive ---------- */
@media (max-width: 768px) {
  .dimension-row {
    grid-template-columns: 1fr;
    text-align: center;
  }
  .dim-bridge {
    flex-direction: row;
    justify-content: center;
  }
  .bridge-cards {
    grid-template-columns: 1fr;
  }
}
</style>

<!-- ═══════════════════════════════════════════════════════════════
     HERO
     ═══════════════════════════════════════════════════════════════ -->
<div class="research-hero">
  <p class="lead-text">
    My research investigates how the complex <strong>Genotype-to-Phenotype map</strong> interacts with natural selection to shape evolutionary outcomes, from genome structure and genetic architecture to organismal diversity.

  </p>
</div>

<!-- ═══════════════════════════════════════════════════════════════
     INTERACTIVE SVG DIAGRAM
     ═══════════════════════════════════════════════════════════════ -->
<div class="research-diagram-wrapper">
<svg viewBox="0 140 760 330" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Research overview diagram showing bridging themes">
  <defs>
    <!-- Gradients for bridges -->
    <linearGradient id="grad-scale" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#FED789"/>
      <stop offset="100%" stop-color="#023743"/>
    </linearGradient>
    <linearGradient id="grad-evo" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#023743"/>
      <stop offset="100%" stop-color="#FED789"/>
    </linearGradient>
    <linearGradient id="grad-approach" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#72874E"/>
      <stop offset="100%" stop-color="#476F84"/>
    </linearGradient>
    <linearGradient id="grad-data" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#A4BED5"/>
      <stop offset="100%" stop-color="#453947"/>
    </linearGradient>

    <!-- Glow filter -->
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <!-- ── Row 1: Biological Scale ── -->
  <!--
  <path class="bridge-arc bridge-arc-1" d="M 130,95 C 250,20 510,20 630,95"
        fill="none" stroke="url(#grad-scale)" stroke-width="2.5" stroke-linecap="round" filter="url(#glow)"/>
  <text x="380" y="38" text-anchor="middle" font-size="11" font-weight="600" fill="url(#grad-scale)" letter-spacing="0.1em">BIOLOGICAL SCALE</text>

  <g class="node-group">
    <rect x="40" y="70" width="180" height="54" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#FED789" stroke-width="1.5"/>
    <text x="130" y="95" text-anchor="middle" font-size="13" font-weight="600" fill="var(--global-text-color, #1c1c1d)">🧬 Molecule</text>
    <text x="130" y="112" text-anchor="middle" font-size="10" fill="var(--global-text-color-light, #828282)">Genome Structure · Regulatory Networks</text>
  </g>

  <g class="node-group">
    <rect x="290" y="70" width="180" height="54" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#72874E" stroke-width="1.5"/>
    <text x="380" y="95" text-anchor="middle" font-size="13" font-weight="600" fill="var(--global-text-color, #1c1c1d)">🦎 Organism</text>
    <text x="380" y="112" text-anchor="middle" font-size="10" fill="var(--global-text-color-light, #828282)">Pleiotropy · G-P map</text>
  </g>

  <g class="node-group">
    <rect x="540" y="70" width="180" height="54" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#023743" stroke-width="1.5"/>
    <text x="630" y="95" text-anchor="middle" font-size="13" font-weight="600" fill="var(--global-text-color, #1c1c1d)">👥 Population</text>
    <text x="630" y="112" text-anchor="middle" font-size="10" fill="var(--global-text-color-light, #828282)">Genetic variance · Fitness landscape</text>
  </g>

  <line x1="220" y1="97" x2="290" y2="97" stroke="var(--global-divider-color, rgba(0,0,0,0.1))" stroke-width="1" stroke-dasharray="4 3"/>
  <line x1="470" y1="97" x2="540" y2="97" stroke="var(--global-divider-color, rgba(0,0,0,0.1))" stroke-width="1" stroke-dasharray="4 3"/>
  -->

  <!-- ── Row 2: Macro ↔ Micro ── -->
  <path class="bridge-arc bridge-arc-2" d="M 155,240 C 260,175 500,175 605,240"
        fill="none" stroke="url(#grad-evo)" stroke-width="2.5" stroke-linecap="round" filter="url(#glow)"/>
  <text x="380" y="190" text-anchor="middle" font-size="13" font-weight="600" fill="url(#grad-evo)" letter-spacing="0.1em">EVOLUTIONARY TIME SCALE</text>

  <!-- Microevolution node -->
  <g class="node-group">
    <rect x="60" y="215" width="190" height="54" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#023743" stroke-width="1.5"/>
    <text x="155" y="248" text-anchor="middle" font-size="15" font-weight="600" fill="var(--global-text-color, #1c1c1d)">🔬 Microevolution</text>
    <text x="155" y="257" text-anchor="middle" font-size="10" fill="var(--global-text-color-light, #828282)"></text>
  </g>

  <!-- Macroevolution node -->
  <g class="node-group">
    <rect x="510" y="215" width="190" height="54" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#FED789" stroke-width="1.5"/>
    <text x="605" y="248" text-anchor="middle" font-size="15" font-weight="600" fill="var(--global-text-color, #1c1c1d)">🌍 Macroevolution</text>
    <text x="605" y="257" text-anchor="middle" font-size="10" fill="var(--global-text-color-light, #828282)"></text>
  </g>

  <!-- ── Row 3: Two bridging dimensions side by side ── -->
  <!-- Statistical ↔ Mechanistic -->
  <path class="bridge-arc bridge-arc-3" d="M 105,400 C 145,345 245,345 285,400"
        fill="none" stroke="url(#grad-approach)" stroke-width="2.5" stroke-linecap="round" filter="url(#glow)"/>
  <text x="195" y="348" text-anchor="middle" font-size="12" font-weight="600" fill="url(#grad-approach)" letter-spacing="0.08em">APPROACH</text>

  <g class="node-group">
    <rect x="25" y="378" width="160" height="76" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#72874E" stroke-width="1.5"/>
    <text x="105" y="403" text-anchor="middle" font-size="14" font-weight="600" fill="var(--global-text-color, #1c1c1d)">📊 Statistical</text>
    <text x="105" y="421" text-anchor="middle" font-size="11" fill="var(--global-text-color-light, #828282)">Quantitative Genetics</text>
    <text x="105" y="438" text-anchor="middle" font-size="11" fill="var(--global-text-color-light, #828282)">Statistical Genetics</text>
  </g>

  <g class="node-group">
    <rect x="205" y="378" width="160" height="76" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#476F84" stroke-width="1.5"/>
    <text x="285" y="403" text-anchor="middle" font-size="14" font-weight="600" fill="var(--global-text-color, #1c1c1d)">⚙️ Mechanistic</text>
    <text x="285" y="421" text-anchor="middle" font-size="11" fill="var(--global-text-color-light, #828282)">Systems Biology</text>
    <text x="285" y="438" text-anchor="middle" font-size="11" fill="var(--global-text-color-light, #828282)">Evo-Devo</text>
  </g>

  <!-- Empirical ↔ Theoretical -->
  <path class="bridge-arc bridge-arc-3" d="M 475,400 C 515,345 615,345 655,400"
        fill="none" stroke="url(#grad-data)" stroke-width="2.5" stroke-linecap="round" filter="url(#glow)"/>
  <text x="565" y="348" text-anchor="middle" font-size="12" font-weight="600" fill="url(#grad-data)" letter-spacing="0.08em">EVIDENCE</text>

  <g class="node-group">
    <rect x="395" y="378" width="160" height="76" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#A4BED5" stroke-width="1.5"/>
    <text x="475" y="403" text-anchor="middle" font-size="14" font-weight="600" fill="var(--global-text-color, #1c1c1d)">🧪 Empirical</text>
    <text x="475" y="421" text-anchor="middle" font-size="11" fill="var(--global-text-color-light, #828282)">Functional Genomics</text>
    <text x="475" y="438" text-anchor="middle" font-size="11" fill="var(--global-text-color-light, #828282)">Population Genomics</text>
  </g>

  <g class="node-group">
    <rect x="575" y="378" width="160" height="76" rx="12" fill="var(--global-card-bg-color, #fff)" stroke="#453947" stroke-width="1.5"/>
    <text x="655" y="403" text-anchor="middle" font-size="14" font-weight="600" fill="var(--global-text-color, #1c1c1d)">📐 Theoretical</text>
    <text x="655" y="421" text-anchor="middle" font-size="11" fill="var(--global-text-color-light, #828282)">Quantitative Genetics</text>
    <text x="655" y="438" text-anchor="middle" font-size="10.5" fill="var(--global-text-color-light, #828282)">Individual-based Modeling</text>
  </g>

  <!-- ── Central anchor ── -->
  <g class="node-group">
    <circle class="center-pulse" cx="380" cy="300" r="32" fill="#453947" opacity="0.15"/>
    <circle cx="380" cy="300" r="22" fill="#453947" opacity="0.9"/>
    <text x="380" y="305" text-anchor="middle" font-size="16" fill="#fff">🌱</text>
  </g>

  <!-- Lines from center to rows -->
  <line x1="380" y1="278" x2="380" y2="210" stroke="#453947" stroke-width="1" stroke-dasharray="4 3" opacity="0.4"/>
  <!-- <line x1="380" y1="278" x2="380" y2="130" stroke="#453947" stroke-width="1" stroke-dasharray="4 3" opacity="0.25"/> -->
  <line x1="360" y1="318" x2="195" y2="365" stroke="#453947" stroke-width="1" stroke-dasharray="4 3" opacity="0.3"/>
  <line x1="400" y1="318" x2="565" y2="365" stroke="#453947" stroke-width="1" stroke-dasharray="4 3" opacity="0.3"/>
</svg>
</div>

<!-- ═══════════════════════════════════════════════════════════════
     BRIDGING DIMENSIONS – Detailed Cards
     ═══════════════════════════════════════════════════════════════ -->

<div class="bridge-section">
  <span class="section-label">Dimension 1</span>
  <h3>Biological Scale: From Molecules to Populations</h3>
  <p style="margin-bottom:1.2rem; color: var(--global-text-color-light); font-size: 0.95rem; line-height: 1.7;">
  </p>
  <div class="bridge-cards">
    <div class="bridge-card accent-scale">
      <span class="card-icon">🧬</span>
      <h4>Molecular</h4>
      <div class="approach-tags">
        <span class="approach-tag">Regulatory network</span>
        <span class="approach-tag">Genome structure</span>
        <span class="approach-tag">Pleiotropy</span>
      </div>
    </div>
    <div class="bridge-card accent-scale">
      <span class="card-icon">🦎</span>
      <h4>Organismal Phenotype</h4>
      <div class="approach-tags">
        <span class="approach-tag">Morphology</span>
        <span class="approach-tag">Development</span>
        <span class="approach-tag">G-to-P map</span>
        <span class="approach-tag">Complex trait</span>
      </div>
    </div>
    <div class="bridge-card accent-scale">
      <span class="card-icon">👥</span>
      <h4>Population</h4>
      <div class="approach-tags">
        <span class="approach-tag">Allelic dynamic</span>
        <span class="approach-tag">Adaptive landscape</span>
        <span class="approach-tag">Variance maintenance</span>
      </div>
    </div>
  </div>
</div>

---

<div class="bridge-section">
  <span class="section-label">Dimension 2</span>
  <h3>Microevolution ↔ Macroevolution</h3>
  <p style="margin-bottom:1.2rem; color: var(--global-text-color-light); font-size: 0.95rem; line-height: 1.7;">
    Can the same principles that govern allele frequency change within populations explain the
    grand patterns of diversity, innovation, and disparity we observe across deep evolutionary time?
    My work seeks to connect population-genetic processes with macroevolutionary outcomes.
  </p>
  <div class="bridge-cards">
    <div class="bridge-card accent-evo">
      <span class="card-icon">🔬</span>
      <h4>Microevolution</h4>
      <p>Within-population processes — selection, drift, mutation, recombination — that drive short-term evolutionary change.</p>
      <div class="approach-tags">
        <!-- <span class="approach-tag">Population genetics</span>
        <span class="approach-tag">Quantitative traits</span>
        <span class="approach-tag">Standing variation</span> -->
      </div>
    </div>
    <div class="bridge-card accent-evo">
      <span class="card-icon">🌍</span>
      <h4>Macroevolution</h4>
      <p>Large-scale patterns of phenotypic diversity, evolutionary novelty, and clade-level dynamics across deep time.</p>
      <div class="approach-tags">
        <!-- <span class="approach-tag">Disparity</span>
        <span class="approach-tag">Innovation</span>
        <span class="approach-tag">Phylogenetics</span> -->
      </div>
    </div>
  </div>
</div>

---

<div class="bridge-section">
  <span class="section-label">Dimension 3</span>
  <h3>Statistical ↔ Mechanistic</h3>
  <p style="margin-bottom:1.2rem; color: var(--global-text-color-light); font-size: 0.95rem; line-height: 1.7;">
    Statistical and quantitative genetics provides powerful predictive frameworks, while systems biology
    and evo-devo reveal the mechanistic architecture that generates and constrains variation. My research
    integrates both paradigms to build a more complete understanding.
  </p>
  <div class="bridge-cards">
    <div class="bridge-card accent-stat">
      <span class="card-icon">📊</span>
      <h4>Statistical / Quantitative Genetics</h4>
      <!-- <p>Variance decomposition, heritability, genetic correlations, and the breeder's equation — powerful tools for prediction without requiring mechanistic detail.</p> -->
      <div class="approach-tags">
        <span class="approach-tag">G-matrix</span>
        <span class="approach-tag">GWAS</span>
        <span class="approach-tag">Genetic architecture</span>
      </div>
    </div>
    <div class="bridge-card accent-mech">
      <span class="card-icon">⚙️</span>
      <h4>Systems Biology / Evo-Devo</h4>
      <!-- <p>Gene regulatory networks, developmental constraints, and mechanistic models of how genotype maps to phenotype — explaining <em>why</em> variation looks the way it does.</p> -->
      <div class="approach-tags">
        <span class="approach-tag">GRNs</span>
        <span class="approach-tag">Developmental bias</span>
        <span class="approach-tag">G-to-P maps</span>
      </div>
    </div>
  </div>
</div>

---

<div class="bridge-section">
  <span class="section-label">Dimension 4</span>
  <h3>Empirical ↔ Theoretical</h3>
  <p style="margin-bottom:1.2rem; color: var(--global-text-color-light); font-size: 0.95rem; line-height: 1.7;">
    <!-- Theory without data is speculation; data without theory is stamp collecting. I combine functional
    genomics experiments with mathematical and computational modeling to generate testable predictions
    and validate them with real biological systems. -->
  </p>
  <div class="bridge-cards">
    <div class="bridge-card accent-emp">
      <span class="card-icon">🧪</span>
      <h4>Functional and Population Genomic Data</h4>
      <!-- <p>High-throughput genomics and transcriptomics - RNA-seq, QTL mapping, epigenetics.</p> -->
      <div class="approach-tags">
        <!-- <span class="approach-tag">RNA-seq</span>
        <span class="approach-tag">QTL mapping</span>
        <span class="approach-tag">Epigenetics</span> -->
      </div>
    </div>
    <div class="bridge-card accent-theo">
      <span class="card-icon">📐</span>
      <h4>Quantitative and Population Genetics Theory</h4>
      <!-- <p>Mathematical frameworks — the multivariate breeder's equation, mutation-selection balance, and models of genetic architecture.</p> -->
      <div class="approach-tags">
        <!-- <span class="approach-tag">Analytical models</span>
        <span class="approach-tag">Individual-based simulation</span> -->
        <!-- <span class="approach-tag">Predictions</span> -->
      </div>
    </div>
  </div>
</div>
