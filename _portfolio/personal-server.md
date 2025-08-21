---
title: "Personal Web & Video Server (C)"
layout: single
permalink: /portfolio/personal-server/
excerpt: "Multithreaded HTTP/1.1 server with static files, JWT authentication, and MP4 streaming."
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
    <p class="project-hero__tagline">Static files · JWT authentication · Video streaming · IPv6</p>

    <p class="project-hero__intro">
      A multithreaded web server written in <strong>C</strong> that serves static content,
      protects private routes with <strong>JWT-based authentication</strong>, and streams
      <strong>MP4 videos</strong> using byte-range requests.
    </p>
  </div>
</section>

<!-- QUICK FACTS -->
<section class="facts">
  <div class="facts-grid">
    <div class="fact-card">
      <h3>Stack</h3>
      <p>C (POSIX sockets, pthreads), libjwt, Jansson</p>
    </div>
    <div class="fact-card">
      <h3>Focus</h3>
      <p>Concurrency, secure auth, and media streaming</p>
    </div>
    <div class="fact-card">
      <h3>Outcome</h3>
      <p>A functional HTTP/1.1 server handling multiple clients, secure endpoints, and smooth video delivery.</p>
    </div>
  </div>
</section>

<!-- GOALS -->
<section class="section-card">
  <h2>Goals</h2>
  <ul>
    <li>Implement a custom HTTP/1.1 server in C.</li>
    <li>Serve static files with correct MIME types.</li>
    <li>Secure private content with cookie-based JWT authentication.</li>
    <li>Support video playback via range requests and partial content.</li>
    <li>Ensure IPv4 and IPv6 compatibility.</li>
  </ul>
</section>

<!-- ARCHITECTURE -->
<section class="section-card">
  <h2>Architecture</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/pserver.png' | relative_url }}" alt="Server architecture diagram">
    <figcaption>
      Requests flow from client → server → routing layer. Endpoints include static files,
      private content (JWT-protected), authentication API, and video API with MP4 streaming.
    </figcaption>
  </figure>

  <div class="callout callout--info">
    <strong>Key features:</strong> JWT cookies for secure access, HTTP/1.1 keep-alive for multiple requests per connection, 
    and range requests for efficient video streaming.
  </div>
</section>

<!-- HOW IT'S BUILT -->
<section class="section-card">
  <h2>How it’s built</h2>

  <div class="stack-badges">
    <span>C (POSIX sockets)</span>
    <span>Pthreads</span>
    <span>libjwt</span>
    <span>Jansson</span>
    <span>HTTP/1.1</span>
  </div>

  <h3>Static Files</h3>
  <ul>
    <li>Serves <code>.html</code>, <code>.css</code>, <code>.js</code>, <code>.svg</code>, and other static content.</li>
    <li>Blocks directory traversal attempts (<code>..</code> in paths).</li>
  </ul>

  <h3>Authentication</h3>
  <ul>
    <li><code>/api/login</code> verifies credentials and issues a signed JWT cookie (<code>HttpOnly; SameSite=Lax</code>).</li>
    <li><code>/api/logout</code> clears the cookie.</li>
    <li>Private endpoints require a valid JWT; expired or invalid tokens are rejected.</li>
  </ul>

  <h3>Video API</h3>
  <ul>
    <li><code>/api/video</code> lists available MP4 files in JSON format.</li>
    <li>Supports <code>Range</code> headers for partial requests (<code>206 Partial Content</code>), enabling smooth streaming and scrubbing.</li>
  </ul>

  <h3>Concurrency & Protocol</h3>
  <ul>
    <li>Threaded design handles multiple clients concurrently.</li>
    <li>HTTP/1.1 keep-alive supported for persistent connections.</li>
    <li>Uses <code>getaddrinfo</code> for IPv4/IPv6 protocol independence.</li>
  </ul>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li>Reliable serving of both public and protected content.</li>
    <li>Secure authentication flow with stateless JWT cookies.</li>
    <li>Concurrent client support without blocking new connections.</li>
    <li>Video streaming with proper range responses for MP4 playback.</li>
  </ul>
</section>

<!-- DEMO -->
<section class="section-card">
  <h2>Demo</h2>
  <p>Demo video recording coming soon.</p>
</section>
