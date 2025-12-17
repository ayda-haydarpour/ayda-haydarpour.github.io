---
title: "Equipment Checkout Kiosk (Web + Google Sheets)"
layout: single
permalink: /portfolio/equipment-kiosk/
excerpt: "Interactive equipment checkout kiosk with live availability, modal checkout, QR instructions, and Google Sheets–backed inventory."
tags: [JavaScript, Frontend, Kiosk, Inventory Systems, Google Sheets, UX, Automation, Web Apps]

author_profile: false
sidebar: []

classes: project-page
teaser: /assets/images/equipment-kiosk.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">Equipment Checkout Kiosk</h1>
    <p class="project-hero__tagline">
      Self-serve kiosk · Live inventory · Modal checkout · QR-based instructions
    </p>

    <p class="project-hero__intro">
      A web-based <strong>equipment checkout kiosk</strong> designed for shared studio and maker spaces.
      Users can browse available kits, view real-time availability, scan QR-based instructions,
      and check out equipment through a streamlined interface. Inventory and loan tracking
      are handled automatically using <strong>Google Sheets</strong>, enabling a zero-backend,
      low-maintenance deployment.
    </p>
  </div>
</section>

<!-- QUICK FACTS -->
<section class="facts">
  <div class="facts-grid">

    <div class="fact-card">
      <div class="fact-icon">
        <img src="{{ '/assets/icons/briefcase.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Stack</h3>
        <p>HTML, CSS, Vanilla JavaScript, Google Sheets (CSV export), Google Forms</p>
      </div>
    </div>

    <div class="fact-card">
      <div class="fact-icon">
        <img src="{{ '/assets/icons/shield-check.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Focus</h3>
        <p>Kiosk UX, frontend systems design, client-side state, data synchronization</p>
      </div>
    </div>

    <div class="fact-card">
      <div class="fact-icon">
        <img src="{{ '/assets/icons/rocket.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>Reliable, zero-backend inventory kiosk with live availability and QR-driven guidance</p>
      </div>
    </div>

  </div>
</section>

<!-- GOALS -->
<section class="section-card">
  <h2>Goals</h2>
  <ul>
    <li>Provide a self-serve interface for browsing and checking out shared equipment.</li>
    <li>Display accurate, real-time availability without manual tracking.</li>
    <li>Prevent checkout when inventory is depleted.</li>
    <li>Log all equipment loans automatically without authentication or servers.</li>
    <li>Enable non-technical staff to manage inventory via Google Sheets.</li>
  </ul>
</section>

<!-- ARCHITECTURE -->
<section class="section-card">
  <h2>Architecture</h2>

  <figure class="figure figure--dark">
    <img src="{{ '/assets/images/equipment-kiosk.png' | relative_url }}" alt="Equipment Checkout Kiosk architecture">
    <figcaption>
      Browser-based kiosk loads static HTML/CSS/JS, reads inventory from <code>kits.json</code>,
      computes availability using loan data pulled from Google Sheets (CSV),
      and submits checkout events via Google Forms.
    </figcaption>
  </figure>

  <div class="callout callout--info">
    <strong>Why this design?</strong>
    It eliminates backend infrastructure entirely while still providing reliable inventory tracking.
    Google Sheets acts as a lightweight data store, and all business logic runs client-side,
    making the system easy to deploy, scale, and maintain.
  </div>
</section>

<!-- HOW IT'S BUILT -->
<section class="section-card">
  <h2>How it’s built</h2>

  <div class="stack-badges">
    <span>Vanilla JavaScript</span>
    <span>Responsive CSS</span>
    <span>Modal UI</span>
    <span>Google Sheets (CSV)</span>
    <span>Google Forms</span>
    <span>QR Code Generation</span>
  </div>

  <h3>Key steps</h3>
  <ol>
    <li><strong>Inventory data:</strong> Equipment metadata stored in <code>kits.json</code> (name, category, quantity, tags, instructions).</li>
    <li><strong>Loan records:</strong> Checkout events logged to Google Sheets via Google Forms.</li>
    <li><strong>Availability logic:</strong> Client-side computation:
      <code>available = total quantity − active loans</code>.
    </li>
    <li><strong>UI rendering:</strong> Kits displayed in a responsive grid with live status badges.</li>
    <li><strong>Modal flow:</strong> “View Details” opens a focused modal for checkout and instructions.</li>
    <li><strong>QR codes:</strong> Dynamically generated QR links to setup or safety documentation.</li>
  </ol>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li><strong>Clear visibility:</strong> Users can instantly see what is available.</li>
    <li><strong>Reduced overhead:</strong> No manual sign-out or staff intervention required.</li>
    <li><strong>Accurate tracking:</strong> Inventory updates automatically after checkout.</li>
    <li><strong>Easy maintenance:</strong> Staff update inventory directly in Google Sheets.</li>
    <li><strong>Successful deployment:</strong> Used as a kiosk-style interface in a shared studio environment.</li>
  </ul>
</section>
