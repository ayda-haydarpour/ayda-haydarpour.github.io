---
layout: single
title: "Ayda Haydarpour"
excerpt: "Cloud & Security • AWS • Systems"
author_profile: false
sidebar: []
classes: home-landing
---

<!-- Hero -->
<section class="hero-landing">
  <div class="hero-inner">
    <h1 class="hero-title">Ayda Haydarpour</h1>
    <p class="hero-subtitle">
      Cloud &amp; Security-Focused Computer Science Student
    </p>
    <p class="hero-intro">
      I’m a senior specializing in <strong>cloud architecture</strong>, <strong>cybersecurity</strong>, and
      <strong>systems development</strong>. I design reliable, scalable solutions with a focus on AWS and security best practices.
    </p>
    <div class="hero-cta">
      <a class="btn btn--primary" href="{{ '/resume.pdf' | relative_url }}" download>Download Resume</a>
      <a class="btn btn--outline" href="mailto:aydahaydarpour@gmail.com">Email Me</a>
    </div>
  </div>
</section>

<!-- Skills (card, exactly like your screenshot) -->
<section class="section panel section-tight">
  <h2>Skills</h2>
  <div class="skills-card">
    <div class="skills-col">
      <h3>Cloud Services</h3>
      <ul>
        <li>AWS: EC2, S3, RDS, VPC, Route 53, CloudFront, IAM, CloudWatch, Auto Scaling, Load Balancing</li>
      </ul>

      <h3>Programming &amp; Scripting</h3>
      <ul>
        <li>Python, Java, C, Bash, JavaScript, HTML/CSS, SQL</li>
      </ul>
    </div>

    <div class="skills-col">
      <h3>Security &amp; Networking</h3>
      <ul>
        <li>IAM policies &amp; access control, Network security, VPNs &amp; Firewalls, Data encryption &amp; hashing, Monitoring &amp; logging, Security best practices (CompTIA+)</li>
      </ul>

      <h3>Tools &amp; Platforms</h3>
      <ul>
        <li>Linux, Git &amp; GitHub, Wireshark, System monitoring tools</li>
      </ul>
    </div>
  </div>
</section>

<!-- Projects (unchanged logic) -->
<section class="section panel section-tight">
  <div class="section-header">
    <h2>Projects</h2>
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

<!-- Media (unchanged) -->
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
