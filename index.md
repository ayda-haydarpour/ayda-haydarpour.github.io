---
layout: single
title: "Ayda Haydarpour"
excerpt: "Cloud & Security • AWS • Systems"
author_profile: false
sidebar: []
classes: home-landing
---

<!-- HERO -->
<section class="hero-landing">
  <div class="hero-inner">
    <h1 class="hero-title">Ayda Haydarpour</h1>
    <p class="hero-subtitle">Cloud &amp; Security-Focused Computer Science Student</p>
    <p class="hero-intro">
      I build practical systems that make life easier — from Raspberry Pi kiosks to production-ready web servers.
      My focus areas are <strong>cloud</strong> (AWS), <strong>security</strong>, and <strong>systems development</strong>.
      I design reliable, scalable solutions with a clean UX and just enough engineering ceremony.
    </p>
    <div class="hero-cta">
      <a class="btn" href="{{ '/assets/Ayda_Haydarpour_Resume.pdf' | relative_url }}">Resume</a>
      <a class="btn btn--outline" href="https://github.com/aydahaydarpour" target="_blank" rel="noopener">GitHub</a>
      <a class="btn btn--outline" href="mailto:ayda@vt.edu">Contact</a>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section class="section panel section-tight" id="skills">
  <h2>Skills</h2>
  <div class="skills-card">
    <div class="skills-col">
      <h3>Cloud Services</h3>
      <ul>
        <li>AWS: EC2, S3, RDS/Aurora, VPC, Route 53, CloudFront, IAM, CloudWatch/CloudTrail, Auto Scaling, ALB/NLB</li>
      </ul>
      <h3>Security</h3>
      <ul>
        <li>Identity &amp; Access (IAM, JWT), network segmentation, TLS/HTTPS, WAF/CDN patterns</li>
      </ul>
    </div>
    <div class="skills-col">
      <h3>Systems &amp; Backend</h3>
      <ul>
        <li>Python (Flask), C (POSIX), Linux, Gunicorn/Systemd, REST APIs</li>
      </ul>
      <h3>Tooling</h3>
      <ul>
        <li>Git/GitHub, Docker/Kubernetes, JSON/CSV data pipelines</li>
      </ul>
    </div>
    <div class="skills-col">
      <h3>Frontend &amp; UX</h3>
      <ul>
        <li>HTML/CSS/JS, Bootstrap, responsive layouts, accessibility basics</li>
      </ul>
      <h3>Hardware</h3>
      <ul>
        <li>Raspberry Pi setup, kiosk mode, HDMI displays, peripherals</li>
      </ul>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section class="section panel" id="projects">
  <h2>Projects</h2>
  <div class="entries-grid entries-grid--wide">

    <!-- NEW) TA Availability Kiosk -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/ta-kiosk/' | relative_url }}">
        <img src="{{ '/assets/images/ta-kiosk.png' | relative_url }}" alt="TA Availability Kiosk (Raspberry Pi + Flask)">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/ta-kiosk/' | relative_url }}">TA Availability Kiosk (Raspberry Pi + Flask)</a>
        </h3>
        <p class="archive__item-excerpt">
          Raspberry Pi kiosk that shows TA schedules with search/filter, live status badges, and QR-to-email.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/ta-kiosk/' | relative_url }}">View</a>
      </div>
    </article>

    <!-- Personal Web & Video Server (C) -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/personal-server/' | relative_url }}">
        <img src="{{ '/assets/images/server.png' | relative_url }}" alt="Personal Web & Video Server (C)">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/personal-server/' | relative_url }}">Personal Web &amp; Video Server (C)</a>
        </h3>
        <p class="archive__item-excerpt">
          Multithreaded HTTP/1.1 server with static files, JWT auth, MP4 streaming, and IPv6 support.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/personal-server/' | relative_url }}">View</a>
      </div>
    </article>

    <!-- Custom Unix Shell (C) -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/custom-shell/' | relative_url }}">
        <img src="{{ '/assets/images/cush.png' | relative_url }}" alt="Custom Unix Shell (C)">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/custom-shell/' | relative_url }}">Custom Unix Shell (C)</a>
        </h3>
        <p class="archive__item-excerpt">
          From-scratch shell with AST parsing, pipelines, I/O redirection, job control, and robust signal handling.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/custom-shell/' | relative_url }}">View</a>
      </div>
    </article>

  </div>
</section>

<!-- MEDIA / PRESS -->
<section class="section panel" id="media">
  <h2>Media</h2>
  <ul class="media-list">
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/forbes.svg' | relative_url }}" alt="Forbes" width="28" height="28" loading="lazy"></span>
      <div class="media-text">
        <strong>Forbes — Afghan Girls Robotics Team Profile</strong>
        <a href="https://www.forbes.com/profile/afghan-girls-robotic-team/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/vt.svg' | relative_url }}" alt="Virginia Tech News" width="28" height="28" loading="lazy"></span>
      <div class="media-text">
        <strong>Virginia Tech News — Student Spotlight (2022)</strong>
        <a href="https://news.vt.edu/articles/2022/09/ayda-haydarpour.html" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
  </ul>
</section>
