---
title: "AWS Multi-Region Resume Site"
layout: single
permalink: /portfolio/aws-multi-region-resume/
excerpt: "Secure, globally distributed static site with failover, access control, and CI/CD."
date: 2025-08-01
tags: [AWS, Security, CloudFront, S3, OAC, CI/CD]

# REMOVE left panel
author_profile: false
sidebar: []

# Page hook for CSS below
classes: project-page
teaser: /assets/images/diagram.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">AWS Multi-Region Resume Site</h1>
    <p class="project-hero__tagline">Secure access control · Multi-region failover · Automated CI/CD</p>
    <div class="project-hero__cta">
      <a class="btn btn--primary" href="#" target="_blank" rel="noopener">Live Demo</a>
      <a class="btn" href="#" target="_blank" rel="noopener">View Repo</a>
    </div>
  </div>
</section>

<!-- INTRO / LEAD -->
<section class="section-card">
  <p class="lead">
    A static resume site with <strong>secure access control</strong>, <strong>multi-region failover</strong>,
    and <strong>automated deployments</strong> from GitHub.
  </p>
</section>

<!-- QUICK FACTS -->
<section class="facts">
  <div class="facts-grid">

    <!-- Stack -->
    <div class="fact-card">
      <div class="fact-icon">
        <!-- briefcase/stack icon -->
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <path d="M10 6h4a2 2 0 0 1 2 2v1h3a1 1 0 0 1 1 1v3H4V10a1 1 0 0 1 1-1h3V8a2 2 0 0 1 2-2Zm-1 3h6V8a1 1 0 0 0-1-1h-4a1 1 0 0 0-1 1v1Z"/>
          <path d="M4 14h16v4a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2v-4Z"/>
        </svg>
      </div>
      <div class="fact-content">
        <h3>Stack</h3>
        <p>CloudFront (OAC, origin groups), S3 (private), IAM, Route 53, GitHub Actions</p>
      </div>
    </div>

    <!-- Focus -->
    <div class="fact-card">
      <div class="fact-icon">
        <!-- shield icon -->
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <path d="M12 3 5 6v6c0 4.97 3.05 8.68 7 9.94 3.95-1.26 7-4.97 7-9.94V6l-7-3Z"/>
          <path d="M9 12l2 2 4-4" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>
      <div class="fact-content">
        <h3>Focus</h3>
        <p>Private-by-default hosting, global delivery, regional failover</p>
      </div>
    </div>

    <!-- Outcome -->
    <div class="fact-card">
      <div class="fact-icon">
        <!-- rocket icon -->
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <path d="M14 3c3.5.5 5.5 2.5 6 6-2.5.5-4.5 1.5-6 3-1.5 1.5-2.5 3.5-3 6-3.5-.5-5.5-2.5-6-6 2.5-.5 4.5-1.5 6-3 1.5-1.5 2.5-3.5 3-6Z"/>
          <circle cx="15.5" cy="8.5" r="1.5" fill="#fff"/>
          <path d="M6 18c.5 1.5 1.5 2.5 3 3 .5-1.5.5-2.5 0-3s-1.5-.5-3 0Z"/>
        </svg>
      </div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>Secure, resilient static site with fast CI/CD</p>
      </div>
    </div>

  </div>
</section>

<!-- GOALS -->
<section class="section-card">
  <h2>Goals</h2>
  <ul>
    <li>Host a static site securely without making S3 buckets public.</li>
    <li>Deliver globally with low latency using CloudFront.</li>
    <li>Set up failover between two AWS regions.</li>
    <li>Automate deployments from GitHub.</li>
  </ul>
</section>

<!-- ARCHITECTURE -->
<section class="section-card">
  <h2>Architecture</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/diagram.png' | relative_url }}" alt="Architecture Diagram">
    <figcaption>CloudFront with OAC, origin-group failover (us-east-1 → eu-west-1), Route 53, S3 private buckets, GitHub Actions for CI/CD.</figcaption>
  </figure>

  <div class="callout callout--info">
    <strong>Why this design?</strong> CloudFront + OAC keeps S3 private; origin groups enable regional failover; GitHub Actions push to both regions and invalidate the CDN for near-instant updates.
  </div>
</section>

<!-- HOW IT'S BUILT -->
<section class="section-card">
  <h2>How it’s built</h2>

  <div class="stack-badges">
    <span>CloudFront (OAC, origin groups)</span>
    <span>S3 (private)</span>
    <span>IAM</span>
    <span>Route 53</span>
    <span>GitHub Actions</span>
  </div>

  <h3>S3 Buckets</h3>
  <ul>
    <li>Two <strong>private</strong> buckets:
      <ul>
        <li><code>ayda-resume-us-east-1</code> (primary)</li>
        <li><code>ayda-resume-eu-west-1</code> (secondary)</li>
      </ul>
    </li>
    <li>Store <code>index.html</code>, <code>style.css</code>, and <code>resume.pdf</code>.</li>
  </ul>

  <h3>CloudFront</h3>
  <ul>
    <li><strong>Origin Access Control (OAC)</strong> so S3 stays private.</li>
    <li><strong>Origin group</strong> with failover (primary us-east-1, secondary eu-west-1).</li>
    <li>Force <strong>HTTPS</strong>; default root object <code>index.html</code>.</li>
  </ul>

  <h3>Security</h3>
  <ul>
    <li>Bucket policies allow only CloudFront (via OAC).</li>
    <li>No public S3 access. Optionally add WAF for extra hardening.</li>
  </ul>

  <h3>CI/CD</h3>
  <ol>
    <li>GitHub Actions sync files to both S3 buckets.</li>
    <li>Invalidate CloudFront so updates go live immediately.</li>
  </ol>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li><strong>Private-by-default hosting</strong> with CDN performance.</li>
    <li><strong>Regional resilience</strong> (automatic failover).</li>
    <li><strong>Fast releases</strong> via CI/CD and cache invalidation.</li>
  </ul>
</section>

<!-- DEMO -->
<section class="section-card">
  <h2>Demo</h2>
  {% include video id="60pCkb77k8s" provider="youtube" %}
</section>
