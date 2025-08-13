---
layout: single
title: "Ayda Haydarpour"
excerpt: "Cloud & Security • AWS • Systems"
author_profile: false   # <-- hide left sidebar on HOME only
sidebar: []             # <-- no sidebar content on HOME
classes: home-landing   # <-- hook for special hero styling
---

<!-- Hero -->
<section class="hero-landing">
  <div class="hero-inner">
    <h1 class="hero-title">Ayda Haydarpour</h1>
    <p class="hero-subtitle">
      I specialize in <strong>cloud architecture</strong>, <strong>cybersecurity</strong>, and
      <strong>end-to-end systems</strong> — with a focus on AWS and secure delivery.
    </p>
    <div class="hero-cta">
      <a class="btn btn--primary" href="{{ '/portfolio/' | relative_url }}">View Projects</a>
      <a class="btn btn--outline" href="{{ '/media/' | relative_url }}">Media</a>
      <a class="btn btn--outline" href="mailto:aydahaydarpour@gmail.com">Contact</a>
    </div>
  </div>
</section>

<!-- Projects Preview -->
<section class="section panel section-tight">
  <div class="section-header">
    <h2>Featured Projects</h2>
    <a class="section-link" href="{{ '/portfolio/' | relative_url }}">See all →</a>
  </div>

  {%- assign items = site.portfolio | sort: 'date' | reverse -%}
  <div class="entries-grid">
  {%- for item in items limit: 4 -%}
    <article class="archive__item panel" style="padding:0;">
      {% if item.teaser %}
      <a class="archive__item-teaser" href="{{ item.url | relative_url }}">
        <img class="teaser--ratio" src="{{ item.teaser | relative_url }}" alt="">
      </a>
      {% endif %}
      <div style="padding:1rem;">
        <h3 class="archive__item-title" style="margin-top:0;">
          <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
        </h3>
        {%- if item.tags and item.tags.size > 0 -%}
        <div class="tags">
          {%- for t in item.tags -%}<span class="tag">{{ t }}</span>{%- endfor -%}
        </div>
        {%- endif -%}
        {%- if item.excerpt -%}
        <p class="archive__item-excerpt">{{ item.excerpt | markdownify | strip_html | truncate: 140 }}</p>
        {%- endif -%}
        <a class="btn btn--primary" href="{{ item.url | relative_url }}">View</a>
      </div>
    </article>
  {%- endfor -%}
  </div>
</section>

<!-- Skills Preview -->
<section class="section panel section-tight">
  <div class="section-header">
    <h2>Skills</h2>
  </div>
  <ul class="pill-list">
    <li>AWS (CloudFront, S3, Route 53, IAM)</li>
    <li>Security (IAM, WAF, Encryption)</li>
    <li>Python</li>
    <li>Java</li>
    <li>Bash</li>
    <li>Git/GitHub</li>
    <li>Linux</li>
    <li>SQL</li>
  </ul>
</section>

<!-- Media Preview -->
<section class="section panel section-tight">
  <div class="section-header">
    <h2>Media & Recognition</h2>
    <a class="section-link" href="{{ '/media/' | relative_url }}">See all →</a>
  </div>
  <ul class="link-list">
    <li><strong>Teen Vogue — 21 Under 21</strong> — <a href="https://www.teenvogue.com/gallery/teen-vogues-21-under-21-2021" target="_blank" rel="noopener">Read</a></li>
    <li><strong>NBC News</strong> — <a href="https://www.nbcnews.com/news/world/afghan-female-robotics-team-defiant-after-fleeing-taliban-qatar-n1277464" target="_blank" rel="noopener">Read</a></li>
    <li><strong>Virginia Tech News</strong> — <a href="https://news.vt.edu/articles/2022/09/ayda-haydarpour.html" target="_blank" rel="noopener">Read</a></li>
  </ul>
</section>

<!-- Contact CTA -->
<section class="section panel section-tight" style="text-align:center;">
  <h2>Get in touch</h2>
  <p>Open to internships and cloud/security projects.</p>
  <p>
    <a class="btn btn--primary" href="mailto:aydahaydarpour@gmail.com">Email Me</a>
    <a class="btn btn--outline" href="https://github.com/ayda-hdp" target="_blank" rel="noopener">GitHub</a>
  </p>
</section>
