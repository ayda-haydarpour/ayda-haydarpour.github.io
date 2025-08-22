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
teaser: /assets/images/ta-kiosk.png
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
        <p>Kiosk UX + Ops: Linux hardening, network setup (DHCP reservation/static IP, mDNS), autostart, logging</p>
      </div>
    </div>

    <!-- Outcome -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/rocket.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>Reliable on-prem kiosk: <code>Available Now</code>/<code>Later Today</code> badges, fast search/filter, one-tap email via QR</p>
      </div>
    </div>

  </div>
</section>

<!-- NETWORKING & IT HIGHLIGHTS -->
<section class="section-card">
  <h2>Networking &amp; IT Highlights</h2>
  <ul>
    <li><strong>Addressing:</strong> Reserved DHCP lease on campus router (or static IP via <code>/etc/dhcpcd.conf</code>) for predictable reachability.</li>
    <li><strong>Hostname &amp; mDNS:</strong> Set <code>ta-kiosk</code> and enabled Avahi for <code>http://ta-kiosk.local</code> discovery on the LAN.</li>
    <li><strong>Reverse Proxy (optional):</strong> Nginx on :80 → proxy_pass to Gunicorn on :5000. Central place for headers, gzip, and logs.</li>
    <li><strong>Firewall:</strong> <code>ufw</code> opened only required ports (80/443 if Nginx; 22 for SSH), default-deny inbound.</li>
    <li><strong>System service:</strong> <code>systemd</code> unit manages Gunicorn (auto-restart on failure, start at boot).</li>
    <li><strong>Logging/Monitoring:</strong> <code>journalctl -u</code> for app/service logs, basic health endpoint (200 check), and cron job to rotate QR cache.</li>
    <li><strong>Secure access:</strong> SSH key-based auth, disabled password login, limited <code>sudo</code>, periodic updates via unattended-upgrades.</li>
    <li><strong>Time sync:</strong> NTP enabled to keep clock accurate for status badges and log timelines.</li>
  </ul>
</section>

<!-- EXECUTION FLOW -->
<section class="section-card">
  <h2>Execution Flow</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/ta-kiosk.png' | relative_url }}" alt="TA Kiosk UI / flow screenshot">
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
    <li><strong>OS &amp; packages:</strong> Raspberry Pi Imager (32-bit), Wi-Fi; <code>sudo apt update &amp;&amp; sudo apt upgrade -y</code>; <code>sudo apt install python3 python3-venv python3-pip ufw avahi-daemon nginx -y</code></li>
    <li><strong>Project:</strong> <code>python3 -m venv venv &amp;&amp; source venv/bin/activate</code>; <code>pip install flask qrcode gunicorn</code></li>
    <li><strong>Gunicorn (dev):</strong> <code>gunicorn -w 2 -b 0.0.0.0:5000 app:app</code></li>
    <li><strong>Firewall:</strong> <code>sudo ufw default deny incoming</code> · <code>sudo ufw allow 22</code> · <em>if using Nginx</em>: <code>sudo ufw allow 80</code> (<code>443</code> if TLS) · <code>sudo ufw enable</code></li>
  </ol>
</section>

<!-- CONFIGURATION SNIPPETS (IT/Networking) -->
<section class="section-card">
  <h2>Configuration Snippets (IT / Networking)</h2>

  <h3>1) Static IP (or reserve via DHCP)</h3>
  <p>Edit <code>/etc/dhcpcd.conf</code> (example on <code>wlan0</code>):</p>
  <pre><code>interface wlan0
static ip_address=192.168.1.50/24
static routers=192.168.1.1
static domain_name_servers=192.168.1.1 1.1.1.1
</code></pre>

  <h3>2) Hostname &amp; mDNS</h3>
  <pre><code>sudo hostnamectl set-hostname ta-kiosk
sudo systemctl enable --now avahi-daemon   # enables http://ta-kiosk.local
</code></pre>

  <h3>3) systemd service for Gunicorn</h3>
  <pre><code># /etc/systemd/system/ta-kiosk.service
[Unit]
Description=TA Kiosk Flask (Gunicorn)
After=network-online.target
Wants=network-online.target

[Service]
User=pi
WorkingDirectory=/home/pi/TAinfo
Environment="PATH=/home/pi/TAinfo/venv/bin"
ExecStart=/home/pi/TAinfo/venv/bin/gunicorn -w 2 -b 127.0.0.1:5000 app:app
Restart=on-failure

[Install]
WantedBy=multi-user.target
</code></pre>
  <pre><code>sudo systemctl daemon-reload
sudo systemctl enable --now ta-kiosk
</code></pre>

  <h3>4) Nginx reverse proxy (optional but recommended)</h3>
  <pre><code># /etc/nginx/sites-available/ta-kiosk
server {
  listen 80;
  server_name ta-kiosk.local;

  location / {
    proxy_set_header Host $host;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_pass http://127.0.0.1:5000;
  }

  location /static/ {
    alias /home/pi/TAinfo/static/;
    access_log off;
    expires 1h;
  }
}
</code></pre>
  <pre><code>sudo ln -s /etc/nginx/sites-available/ta-kiosk /etc/nginx/sites-enabled/
sudo nginx -t &amp;&amp; sudo systemctl reload nginx
</code></pre>

  <h3>5) SSH hardening</h3>
  <pre><code># Generate key on laptop, then copy to Pi
ssh-keygen -t ed25519 -C "ayda@kiosk"
ssh-copy-id pi@ta-kiosk.local

# Disable password auth
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication no/' /etc/ssh/sshd_config
sudo systemctl reload ssh
</code></pre>

  <h3>6) Kiosk mode (Chromium)</h3>
  <p>Launch Chromium to the local site on login (LXDE autostart):</p>
  <pre><code># ~/.config/lxsession/LXDE-pi/autostart
@/usr/bin/chromium-browser --kiosk --incognito http://ta-kiosk.local/
</code></pre>

  <h3>7) Health check &amp; logs</h3>
  <pre><code># simple health check (returns 200)
curl -s -o /dev/null -w "%{http_code}\n" http://127.0.0.1:5000/

# service logs
journalctl -u ta-kiosk -f
</code></pre>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li>Consistent, predictable access via <code>ta-kiosk.local</code> or static IP; reverse proxy centralizes logging.</li>
    <li>Hardened Pi: key-only SSH, minimal open ports, auto-recovery via systemd on failures.</li>
    <li>Instant search across TA name, class, days, and email with readable, kiosk-safe UI.</li>
    <li>One-tap contact via QR; static assets cached for snappy loads.</li>
  </ul>
</section>

<!-- NEXT -->
<section class="section-card">
  <h2>Next</h2>
  <ul>
    <li>TLS (self-signed or internal CA) and HSTS at Nginx.</li>
    <li>Prometheus node_exporter + Grafana or simple <code>nginx_status</code> for basic metrics.</li>
    <li>Admin page for roster edits and CSV import/export.</li>
  </ul>
</section>
