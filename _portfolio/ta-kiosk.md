---
title: "TA Availability Kiosk (Raspberry Pi + Flask)"
layout: single
permalink: /portfolio/ta-kiosk/
excerpt: "Raspberry Pi kiosk with hardened Linux, systemd services, network configuration (DHCP/static IP, mDNS), reverse proxy, and monitoring—serving a Flask app with search/filter, live status, and QR-to-email."
tags: [Python, Flask, Raspberry Pi, Kiosk, Networking, Linux, Systemd, Nginx, Security, QR, Bootstrap]

author_profile: false
sidebar: []

# Page hook for CSS
classes: project-page

# Thumbnail/teaser for cards
teaser: /assets/images/kiosk.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">TA Availability Kiosk (Raspberry Pi + Flask)</h1>
    <p class="project-hero__tagline">Flask · Search &amp; Filter · Live Status · QR Codes · Linux Hardening · Network Config</p>

    <p class="project-hero__intro">
      A self-serve kiosk app that runs on a <strong>Raspberry Pi</strong> and displays Teaching Assistants’ <strong>classes</strong>, <strong>days/times</strong>, and <strong>email</strong>—backed by production-minded <strong>networking</strong>, <strong>systemd</strong>, and <strong>security</strong> configuration. TAs can be found via <strong>search</strong> or filtered by <strong>class + day</strong>. Each TA has a <strong>QR code</strong> that opens a pre-filled email for quick contact.
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
        <p>Python 3, Flask, Gunicorn, Bootstrap; Raspberry Pi OS; optional Nginx reverse proxy</p>
      </div>
    </div>

    <!-- Focus -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/shield-check.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Focus</h3>
        <p>Kiosk UX + Ops; Linux hardening; network config (DHCP/static IP, mDNS); autostart; logging &amp; monitoring</p>
      </div>
    </div>

    <!-- Outcome -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/rocket.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>Reliable on-prem kiosk with <code>Available Now</code>/<code>Later Today</code> badges, fast search/filter, and one-tap email via QR</p>
      </div>
    </div>

  </div>
</section>

<!-- NETWORKING & IT SETUP -->
<section class="section-card">
  <h2>Networking &amp; IT Setup</h2>
  <ul>
    <li>Reserved static IP / DHCP lease for predictable kiosk access</li>
    <li>mDNS discovery (<code>ta-kiosk.local</code>) for easy LAN access</li>
    <li>Reverse proxy with Nginx for centralized logging &amp; headers</li>
    <li>Firewall rules with <code>ufw</code> (default deny; allow 22/80/443 only)</li>
    <li><code>systemd</code> service ensures Gunicorn auto-start &amp; recovery</li>
    <li>SSH hardened with key-based auth; password login disabled</li>
    <li>Health checks &amp; logs monitored via <code>journalctl</code> + cron jobs</li>
  </ul>
  <p><em>Note:</em> Full configuration files and setup scripts are available in my GitHub repo.</p>
</section>

<!-- EXECUTION FLOW -->
<section class="section-card">
  <h2>Execution Flow</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/kiosk.png' | relative_url }}" alt="TA Kiosk UI / flow screenshot">
    <figcaption>
      Chromium in kiosk mode loads the Flask UI through Gunicorn (optionally via Nginx). JS computes availability badges;
      QR images resolve to mailto links. Static assets (CSS/QR) served from <code>/static</code>.
    </figcaption>
  </figure>
</section>

<!-- HOW IT'S BUILT -->
<section class="section-card">
  <h2>How it’s built</h2>

  <div class="stack-badges">
    <span>Flask App</span>
    <span>Gunicorn WSGI</span>
    <span>Systemd Autostart</span>
    <span>Nginx (optional)</span>
    <span>QR Code Generation</span>
    <span>JSON Data</span>
  </div>

  <h3>Key behaviors</h3>
  <ul>
    <li><strong>Endpoints:</strong> <code>/</code> UI; <code>/get_ta_info</code> (by name); <code>/filter_tas</code> (class+day); <code>/search_tas</code> (name/class/email/text).</li>
    <li><strong>Data:</strong> <code>ta_data.json</code> drives roster &amp; schedule; edits show on reload.</li>
    <li><strong>QR codes:</strong> Pre-generated into <code>static/qr_codes/</code> on startup; each encodes a <code>mailto:</code> deep link.</li>
    <li><strong>Status badges:</strong> Client-side JS computes <em>Available Now</em> / <em>Later Today</em> / <em>Offline</em> using current weekday/hour.</li>
    <li><strong>Styling:</strong> Bootstrap + custom CSS using VT maroon (<code>#630031</code>) and orange (<code>#CF4420</code>).</li>
  </ul>
</section>

<!-- SETUP & RUN -->
<section class="section-card">
  <h2>Setup &amp; Run</h2>
  <ol>
    <li><strong>OS &amp; packages:</strong> Raspberry Pi Imager, Wi-Fi; <code>sudo apt update &amp;&amp; sudo apt upgrade -y</code>; <code>sudo apt install python3 python3-venv python3-pip ufw avahi-daemon nginx -y</code></li>
    <li><strong>Project:</strong> <code>python3 -m venv venv &amp;&amp; source venv/bin/activate</code>; <code>pip install flask qrcode gunicorn</code></li>
    <li><strong>Gunicorn (dev):</strong> <code>gunicorn -w 2 -b 0.0.0.0:5000 app:app</code></li>
    <li><strong>Firewall:</strong> <code>sudo ufw default deny incoming</code> · <code>sudo ufw allow 22</code> · <em>if using Nginx</em>: <code>sudo ufw allow 80</code> (<code>443</code> if TLS) · <code>sudo ufw enable</code></li>
  </ol>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li>Consistent access via <code>ta-kiosk.local</code> or static IP; reverse proxy centralizes logs.</li>
    <li>Hardened Pi: key-only SSH, minimal open ports, auto-recovery via systemd.</li>
    <li>Instant search across TA name, class, days, and email with kiosk-safe UI.</li>
    <li>One-tap contact via QR; static assets cached for snappy loads.</li>
  </ul>
</section>

<!-- NEXT -->
<section class="section-card">
  <h2>Next</h2>
  <ul>
    <li>TLS (self-signed or internal CA) and HSTS at Nginx.</li>
    <li>Prometheus node_exporter + Grafana or simple <code>nginx_status</code> for metrics.</li>
    <li>Admin page for roster edits and CSV import/export.</li>
  </ul>
</section>
