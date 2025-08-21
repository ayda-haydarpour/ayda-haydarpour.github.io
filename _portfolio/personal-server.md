---
title: "Personal Web & Video Server (C)"
layout: single
permalink: /portfolio/personal-server/
excerpt: "HTTP/1.1 server with static files, JWT cookie auth, HTML5 fallback, MP4 range streaming, concurrency, and IPv6 support."
tags: [C, Systems, UNIX, Networking, HTTP, Security]

author_profile: false
sidebar: []

# Page hook for CSS
classes: project-page

# Thumbnail/teaser for cards
teaser: /assets/images/pserver.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">Personal Web &amp; Video Server (C)</h1>
    <p class="project-hero__tagline">HTTP/1.1 · JWT Auth · MP4 Streaming · Concurrency · IPv6</p>

    <p class="project-hero__intro">
      A small yet capable web server written in <strong>C</strong> that serves files, implements stateless <strong>JWT cookie authentication</strong>,
      supports <strong>HTML5 fallback</strong> for SPA routes, handles <strong>MP4 streaming with byte-range requests</strong>, and accepts multiple
      clients concurrently with <strong>HTTP/1.1 keep-alive</strong> and <strong>protocol independence</strong> (IPv4/IPv6). Functionality follows the course spec and was built from an HTTP starter in C with POSIX sockets.
    </p>
  </div>
</section>

<style>
/* Match the hero code style you used on the shell page (no white pill) */
.project-hero code, .project-hero kbd {
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
        <p>C (POSIX), pthreads/threaded design, sockets (TCP), <code>getaddrinfo</code>, <code>bind</code>, <code>listen</code>, <code>accept</code>, <code>recv</code>/<code>send</code>, <code>sendfile</code>, <code>stat</code>, <code>opendir</code>, Jansson &amp; libjwt.</p>
      </div>
    </div>

    <!-- Focus -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/shield-check.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Focus</h3>
        <p>HTTP/1.1 parsing &amp; keep-alive, secure cookie auth (HS256), HTML5 SPA fallback, MP4 range streaming, robust error handling.</p>
      </div>
    </div>

    <!-- Outcome -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/rocket.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>Serves static and private content, lists/streams videos, validates tokens, resists directory traversal, and handles concurrent clients cleanly.</p>
      </div>
    </div>

  </div>
</section>

<!-- FUNCTIONALITY -->
<section class="section-card">
  <h2>Functionality</h2>
  <ul>
    <li><strong>Static files</strong> under a server root; correct MIME types (.html/.css/.js/.svg/.mp4) and directory-traversal protection (<code>..</code> rejected).:contentReference[oaicite:1]{index=1}:contentReference[oaicite:2]{index=2}</li>
    <li><strong>Authentication</strong> via <code>/api/login</code> (POST): verifies username/password, issues HS256-signed JWT in an <code>HttpOnly; SameSite=Lax</code> cookie (<code>auth_jwt</code>), and returns claims (<code>sub</code>, <code>iat</code>, <code>exp</code>). <code>/api/logout</code> clears cookie; <code>/api/login</code> (GET) reflects valid claims.:contentReference[oaicite:3]{index=3}:contentReference[oaicite:4]{index=4}</li>
    <li><strong>HTML5 fallback</strong> (with <code>-a</code>): serve <code>/index.html</code>, <code>path.html</code> if present, otherwise <code>/200.html</code> for SPA routes.:contentReference[oaicite:5]{index=5}:contentReference[oaicite:6]{index=6}</li>
    <li><strong>MP4 streaming</strong>: advertises <code>Accept-Ranges: bytes</code>, parses <code>Range:</code> and responds with <code>206 Partial Content</code>/<code>Content-Range</code>. <code>/api/video</code> lists available <code>.mp4</code> (name, size).:contentReference[oaicite:7]{index=7}:contentReference[oaicite:8]{index=8}</li>
    <li><strong>Concurrency</strong>: accepts multiple clients; supports HTTP/1.1 keep-alive. Implemented with a thread-based approach.:contentReference[oaicite:9]{index=9}:contentReference[oaicite:10]{index=10}</li>
    <li><strong>Protocol independence</strong>: uses <code>getaddrinfo</code>; compatible with IPv4/IPv6.:contentReference[oaicite:11]{index=11}</li>
  </ul>
</section>

<!-- EXECUTION FLOW -->
<section class="section-card">
  <h2>Execution Flow</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/pserver-flow.png' | relative_url }}" alt="Execution flow: request parsing, routing to static/private/API, streaming with Range, and keep-alive handling">
    <figcaption>Request → routing (static / private / API). Private requires valid JWT. MP4 handlers set <code>Accept-Ranges</code> and optional <code>Content-Range</code>. Connection stays open for HTTP/1.1 keep-alive.</figcaption>
  </figure>
</section>

<!-- HOW IT'S BUILT -->
<section class="section-card">
  <h2>How it’s built</h2>

  <div class="stack-badges">
    <span>HTTP Parser</span>
    <span>JWT Cookies</span>
    <span>HTML5 Fallback</span>
    <span>Range Streaming</span>
    <span>IPv6-Ready</span>
  </div>

  <h3>Key behaviors</h3>
  <ul>
    <li><strong>Header processing:</strong> parses <code>Content-Length</code>, <code>Cookie</code> (extracts <code>auth_jwt</code>), and <code>Range</code> for videos.:contentReference[oaicite:12]{index=12}</li>
    <li><strong>JWT flow:</strong> validates signature and <code>exp</code>; rejects expired/invalid tokens; protects <code>/private</code> with verification.:contentReference[oaicite:13]{index=13}</li>
    <li><strong>Security hygiene:</strong> blocks <code>..</code> traversal; returns precise status codes (<code>403</code>, <code>404</code>, <code>405</code>, <code>416</code>/<code>206</code> cases).:contentReference[oaicite:14]{index=14}</li>
    <li><strong>Streaming:</strong> calculates byte ranges, sets <code>206</code> + <code>Content-Range</code>, and loops <code>sendfile</code> to transmit segments. Lists <code>.mp4</code> using <code>opendir</code>/<code>readdir</code>/<code>stat</code>.:contentReference[oaicite:15]{index=15}</li>
    <li><strong>Keep-alive:</strong> returns <code>Connection: keep-alive</code> for HTTP/1.1 and <code>close</code> for 1.0, matching client version.:contentReference[oaicite:16]{index=16}</li>
  </ul>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li>Served public and protected content with stateless JWT cookies and proper SameSite/HttpOnly attributes.:contentReference[oaicite:17]{index=17}</li>
    <li>Handled concurrent clients without starving new accepts; robust to malformed requests.:contentReference[oaicite:18]{index=18}</li>
    <li>Streamed MP4 smoothly with accurate <code>206</code>/<code>Content-Range</code> and advertised <code>Accept-Ranges</code>.:contentReference[oaicite:19]{index=19}</li>
    <li>Supported SPA routing via HTML5 fallback when enabled.:contentReference[oaicite:20]{index=20}</li>
  </ul>
</section>

<!-- (Optional) DEMO -->
<section class="section-card">
  <h2>Demo</h2>
  <p>Add a short terminal GIF or a YouTube link of: login → view private page → list videos via <code>/api/video</code> → stream a clip with byte-range seeks.</p>
</section>
