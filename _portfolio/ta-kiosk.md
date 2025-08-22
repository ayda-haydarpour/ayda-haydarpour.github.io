---
title: "TA Availability Kiosk (Raspberry Pi + Flask)"
layout: single
permalink: /portfolio/ta-kiosk/
excerpt: "Raspberry Pi-powered kiosk that shows TA availability with search/filter, live status badges, and QR-to-email."
tags: [Python, Flask, Raspberry Pi, Kiosk, Web, QR, Bootstrap]

author_profile: false
sidebar: []

# Page hook for CSS
classes: project-page

# Thumbnail/teaser for cards
teaser: /assets/images/ta-kiosk.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">TA Availability Kiosk (Raspberry Pi + Flask)</h1>
    <p class="project-hero__tagline">Flask · Search &amp; Filter · Live Status · QR Codes</p>

    <p class="project-hero__intro">
      A self-serve kiosk app that runs on a <strong>Raspberry Pi</strong> and displays Teaching Assistants’ <strong>classes</strong>, <strong>days/times</strong>, and <strong>email</strong>. TAs can be found via <strong>search</strong> or filtered by <strong>class + day</strong>. Each TA has a <strong>QR code</strong> that opens a pre-filled email for quick contact.
    </p>
  </div>
</section>

<style>
/* Remove code “pill” styling in the blue hero only (no white background) */
.project-hero code,
.project-hero kbd {
  background: transparent !important;
  padding: 0 !important;
  border: 0 !important;
  box-shadow: none !important;
  font-family: inherit;
  font-weight: 700;
}
</style>

<!-- QUICK FACTS -->
<section class="facts">
  <div class="facts-grid">

    <!-- Stack -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/briefcase.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Stack</h3>
        <p>Python 3, Flask, Gunicorn, Bootstrap, qrcode; Raspberry Pi OS</p>
      </div>
    </div>

    <!-- Focus -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/shield-check.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Focus</h3>
        <p>Kiosk UX, simple operations, quick lookup, consistent styling (VT maroon/orange)</p>
      </div>
    </div>

    <!-- Outcome -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/rocket.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>Fast TA discovery with <code>Available Now</code>/<code>Later Today</code> status badges, one-tap email via QR</p>
      </div>
    </div>

  </div>
</section>

<!-- GOALS -->
<section class="section-card">
  <h2>Goals</h2>
  <ul>
    <li>Provide a clean, kiosk-friendly UI with search and class/day filtering.</li>
    <li>Show a live availability status based on the current day/time.</li>
    <li>Generate per-TA QR codes to launch a pre-filled email.</li>
    <li>Keep data editable via a simple JSON file for easy updates.</li>
  </ul>
</section>

<!-- EXECUTION FLOW -->
<section class="section-card">
  <h2>Execution Flow</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/ta-kiosk.png' | relative_url }}" alt="TA Kiosk UI screenshot">
    <figcaption>
      The Flask app serves an interactive page: search by name/class/day/email, or filter by class + day.
      Status badges reflect the current time; QR codes open “mailto” links for quick outreach.
    </figcaption>
  </figure>
</section>

<!-- HOW IT'S BUILT -->
<section class="section-card">
  <h2>How it’s built</h2>

  <div class="stack-badges">
    <span>Flask App</span>
    <span>Bootstrap UI</span>
    <span>QR Code Generation</span>
    <span>Class/Day Filters</span>
    <span>JSON Data</span>
  </div>

  <h3>Key behaviors</h3>
  <ul>
    <li><strong>Endpoints:</strong> <code>/</code> serves the kiosk UI; <code>/get_ta_info</code> returns a single TA by name; <code>/filter_tas</code> returns TAs for a class+day; <code>/search_tas</code> returns matches across name, class, availability text, and email.</li>
    <li><strong>Data:</strong> TA roster &amp; schedule are stored in a simple <code>ta_data.json</code> file; updates appear on reload.</li>
    <li><strong>QR codes:</strong> Generated at startup into <code>static/qr_codes/</code>; each encodes a <code>mailto:</code> link with a subject.</li>
    <li><strong>Status badges:</strong> JS computes <em>Available Now</em> / <em>Later Today</em> / <em>Offline</em> based on the current weekday and hour.</li>
    <li><strong>Styling:</strong> Bootstrap + custom CSS using VT maroon (<code>#630031</code>) and orange (<code>#CF4420</code>).</li>
  </ul>
</section>

<!-- SETUP & RUN -->
<section class="section-card">
  <h2>Setup &amp; Run</h2>
  <ol>
    <li><strong>Raspberry Pi OS:</strong> Flash with Raspberry Pi Imager; connect HDMI, keyboard, mouse, Wi-Fi.</li>
    <li><strong>System update:</strong> <code>sudo apt update &amp;&amp; sudo apt upgrade -y</code></li>
    <li><strong>Python &amp; venv:</strong> <code>sudo apt install python3 python3-pip python3-venv -y</code></li>
    <li><strong>Project:</strong> <code>python3 -m venv venv &amp;&amp; source venv/bin/activate</code>; <code>pip install flask qrcode gunicorn</code></li>
    <li><strong>Run (dev):</strong> <code>python app.py</code></li>
    <li><strong>Run (prod):</strong> <code>gunicorn -w 2 -b 0.0.0.0:5000 app:app</code> (change port if needed)</li>
  </ol>
  <p><em>Tip:</em> Autostart on boot (systemd service) and kiosk-mode browser are easy next steps.</p>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li>Instant search across TA name, class, days, and email.</li>
    <li>Clear class+day filtering with readable schedules.</li>
    <li>QR-to-email reduces friction for students contacting TAs.</li>
    <li>Lightweight operations: edit a JSON file to update rosters.</li>
  </ul>
</section>

<!-- NEXT -->
<section class="section-card">
  <h2>Next</h2>
  <ul>
    <li>Systemd autostart for Gunicorn on boot.</li>
    <li>CSV import/export for TA rosters.</li>
    <li>Admin page for edits without SSH.</li>
  </ul>
</section>
