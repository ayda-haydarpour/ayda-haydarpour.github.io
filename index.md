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
      I’m a fourth year Computer Science student specializing in <strong>cloud architecture</strong>, <strong>cybersecurity</strong>, and
      <strong>systems development</strong>. I design reliable, scalable solutions with a focus on AWS and security best practices.
    </p>
  </div>
</section>

<!-- SKILLS -->
<section class="section panel section-tight" id="skills">
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
        <li>IAM policies &amp; access control, Network security, VPNs &amp; Firewalls, Data encryption &amp; hashing,
            Monitoring &amp; logging, Security best practices (CompTIA+)</li>
      </ul>
      <h3>Tools &amp; Platforms</h3>
      <ul>
        <li>Linux, Git &amp; GitHub, Wireshark, System monitoring tools</li>
      </ul>
    </div>
  </div>
</section>

<!-- PROJECTS (collapsible: shows 4, expands inline) -->
<section class="section panel section-tight" id="projects">
  <div class="section-header">
    <h2>Projects</h2>
    <button class="section-link as-link" data-toggle="#projects-grid">See all →</button>
  </div>

  {%- assign items = site.portfolio | sort: 'date' | reverse -%}
  <div id="projects-grid" class="entries-grid entries-grid--compact is-collapsed" data-collapse="4">
  {%- for item in items -%}
    <article class="archive__item panel card--compact">
      {% if item.teaser %}
      <a class="archive__item-teaser teaser--compact" href="{{ item.url | relative_url }}">
        <img src="{{ item.teaser | relative_url }}" alt="">
      </a>
      {% endif %}
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
        </h3>
        {%- if item.excerpt -%}
        <p class="archive__item-excerpt">{{ item.excerpt | markdownify | strip_html | truncate: 110 }}</p>
        {%- endif -%}
        <a class="btn btn--sm" href="{{ item.url | relative_url }}">View</a>
      </div>
    </article>
  {%- endfor -%}
  </div>
</section>

<!-- MEDIA (first 4 with icons; rest text-only; collapsible) -->
<section class="section panel section-tight" id="media">
  <div class="section-header">
    <h2>Media & Recognition</h2>
    <button class="section-link as-link" data-toggle="#media-list">See all →</button>
  </div>

  <ul id="media-list" class="media-list is-collapsed show-4" data-collapse="4">
    <!-- 1) WITH ICON -->
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/vogue.svg' | relative_url }}" alt="Teen Vogue" width="28" height="28" loading="lazy"></span>
      <div class="media-text"><strong>Teen Vogue — 21 Under 21 (2021)</strong>
        <a href="https://www.teenvogue.com/gallery/teen-vogues-21-under-21-2021" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <!-- 2) WITH ICON -->
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/nbc.svg' | relative_url }}" alt="NBC News" width="28" height="28" loading="lazy"></span>
      <div class="media-text"><strong>NBC News — Afghan Female Robotics Team Defiant After Fleeing Taliban</strong>
        <a href="https://www.nbcnews.com/news/world/afghan-female-robotics-team-defiant-after-fleeing-taliban-qatar-n1277464" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <!-- 3) WITH ICON -->
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/forbes.svg' | relative_url }}" alt="Forbes" width="28" height="28" loading="lazy"></span>
      <div class="media-text"><strong>Forbes — Afghan Girls Robotics Team Profile</strong>
        <a href="https://www.forbes.com/profile/afghan-girls-robotic-team/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <!-- 4) WITH ICON -->
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/vt.svg' | relative_url }}" alt="Virginia Tech News" width="28" height="28" loading="lazy"></span>
      <div class="media-text"><strong>Virginia Tech News — Student Spotlight (2022)</strong>
        <a href="https://news.vt.edu/articles/2022/09/ayda-haydarpour.html" target="_blank" rel="noopener">Read</a>
      </div>
    </li>

    <!-- 5+) NO ICON (add class="no-icon" and omit icon span) -->
    <li class="no-icon">
      <div class="media-text"><strong>Virginia Tech News — Afghan Dreamers / Rule Breakers (2025)</strong>
        <a href="https://news.vt.edu/articles/2025/04/Afghan-Dreamers-Rule-Breakers-Ayda-Haydarpour-student.html" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>Virginia Public Radio</strong>
        <a href="https://virginiapublicradio.com/2022/09/01/robotics-champion-fled-afghanistan-now-shes-studying-at-virginia-tech/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>WVTF Public Radio</strong>
        <a href="https://www.wvtf.org/news/2022-09-01/robotics-champion-fled-afghanistan-now-shes-studying-at-virginia-tech" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>France 24</strong>
        <a href="https://first.global/in-the-news/france-24-afghan-girls-robotics-team-design-their-future-in-qatar/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>Macaroni Kid NRV</strong>
        <a href="https://nrv.macaronikid.com/articles/6411e7794a01232a11181e2e/ymca-at-virginia-tech-celebrates-women-in-innovation-and-technology" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>RFI</strong>
        <a href="https://www.rfi.fr/en/business-and-tech/20210922-afghan-girls-robotics-team-design-their-future-in-qatar" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>Nippon.com</strong>
        <a href="https://www.nippon.com/en/news/reu20210827KBN2FR1JN/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>Reuters</strong>
        <a href="https://www.reuters.com/world/asia-pacific/dont-abandon-afghanistan-pleads-member-afghan-all-female-robotics-team-2021-08-26/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>Al-Fanar Media</strong>
        <a href="https://www.al-fanarmedia.org/2021/09/afghanistans-all-female-robotics-team-continues-building-robots-in-qatar/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>Qatar Foundation</strong>
        <a href="https://www.qf.org.qa/stories/qatar-has-been-the-gateway-to-a-better-life-for-us-says-captain-of-afghan" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>Qatar Day</strong>
        <a href="https://www.qatarday.com/dont-abandon-afghanistan-pleads-member-of-afghan-all-female-robotics-team" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>Kuwait Times</strong>
        <a href="https://kuwaittimes.com/afghan-robotics-team-design-future-in-qatar/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li class="no-icon">
      <div class="media-text"><strong>WISE — Ayda Haydarpour Biography</strong>
        <a href="https://www.wise-qatar.org/biography/ayda-haydarpour/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
  </ul>
</section>

<!-- SASS-SAFE toggler JS -->
<script>
document.addEventListener('DOMContentLoaded', () => {
  document.querySelectorAll('.is-collapsed[data-collapse]').forEach(box => {
    const n = parseInt(box.dataset.collapse || '4', 10);
    box.classList.add(`show-${n}`);
  });
});

document.addEventListener('click', (e) => {
  const btn = e.target.closest('[data-toggle]');
  if (!btn) return;

  const sel = btn.getAttribute('data-toggle');
  const box = document.querySelector(sel);
  if (!box) return;

  const expanded = box.classList.toggle('is-expanded');
  box.classList.toggle('is-collapsed', !expanded);
  btn.textContent = expanded ? 'Show less ↑' : 'See all →';
});
</script>
