---
title: "Personal Web & Video Server (C)"
layout: single
permalink: /portfolio/personal-server/
excerpt: "HTTP/1.1 web server in C with JWT auth, MP4 streaming, and IPv6 support."
tags: [C, Systems, Networking, HTTP, Security]

author_profile: false
sidebar: []

classes: project-page
teaser: /assets/images/pserver.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">Personal Web &amp; Video Server (C)</h1>
    <p class="project-hero__tagline">Static Files · JWT Auth · Video Streaming · IPv6</p>

    <p class="project-hero__intro">
      A lightweight web server built from scratch in <strong>C</strong>.  
      It serves static files, protects private routes with <strong>JWT authentication</strong>, supports
      <strong>MP4 video streaming with byte ranges</strong>, and runs over both IPv4 and IPv6.
    </p>
  </div>
</section>

<!-- QUICK FACTS -->
<section class="facts">
  <div class="facts-grid">
    <div class="fact-card">
      <h3>Stack</h3>
      <p>C (POSIX), sockets, pthreads, libjwt, Jansson</p>
    </div>
    <div class="fact-card">
      <h3>Focus</h3>
      <p>Concurrency, security, streaming</p>
    </div>
    <div class="fact-card">
      <h3>Outcome</h3>
      <p>A functional HTTP/1.1 server that handles multiple clients and secure content.</p>
    </div>
  </div>
</section>

<!-- FUNCTIONALITY -->
<section class="section-card">
  <h2>What it does</h2>
  <ul>
    <li>📄 Serves static files with correct MIME types</li>
    <li>🔒 Protects <code>/private</code> with JWT cookie auth</li>
    <li>🎬 Streams MP4 videos with <code>206 Partial Content</code></li>
    <li>🔑 Provides <code>/api/login</code>, <code>/api/logout</code>, and <code>/api/video</code></li>
    <li>🌍 Supports both IPv4 and IPv6</li>
  </ul>
</section>

<!-- EXECUTION FLOW -->
<section class="section-card">
  <h2>Execution Flow</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/pserver.png' | relative_url }}" alt="Personal Server diagram">
    <figcaption>Client requests → Server routes to static, private, or API endpoints → Responses with files, JSON, or streamed video.</figcaption>
  </figure>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li>Handled concurrent requests reliably</li>
    <li>Delivered secure, cookie-based auth</li>
    <li>Streamed videos smoothly with range requests</li>
  </ul>
</section>

<!-- DEMO -->
<section class="section-card">
  <h2>Demo</h2>
  <p>Recorded video coming soon.</p>
</section>
