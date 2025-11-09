---
layout: single
title: "Ayda Haydarpour"
excerpt: "Cloud & AI • AWS • Systems"
author_profile: false
sidebar: []
classes: home-landing
---

<!-- HERO -->
<section class="hero-landing">
  <div class="hero-inner">
    <h1 class="hero-title">Ayda Haydarpour</h1>
    <p class="hero-subtitle">Cloud &amp; AI-Focused Computer Science Student</p>
    <p class="hero-intro">
      I’m a fourth year Computer Science student specializing in <strong>cloud engineering</strong> and
      <strong>AI-driven solutions</strong>, with a strong foundation in software development, and I’m an
      <strong>AWS Certified Solutions Architect – Associate</strong>. I design scalable, secure, and impactful systems
      using AWS and modern best practices.
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
      <h3>AI &amp; Data</h3>
      <ul>
        <li>Machine Learning (TensorFlow, scikit-learn), Data analysis, K-Means clustering, SQL for data work</li>
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

<!-- PROJECTS — GRID -->
<section class="section panel section-tight" id="projects">
  <div class="section-header">
    <h2>Projects</h2>
  </div>

  <div class="entries-grid--wide">
    <!-- 1) AWS Multi-Region Resume -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/aws-multi-region-resume/' | relative_url }}">
        <img src="{{ '/assets/images/diagram.png' | relative_url }}" alt="AWS Multi-Region Resume architecture">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/aws-multi-region-resume/' | relative_url }}">AWS Multi-Region Resume Site</a>
        </h3>
        <p class="archive__item-excerpt">
          Secure, globally distributed static site with Route 53 failover, CloudFront, S3 origin access, and CI/CD.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/aws-multi-region-resume/' | relative_url }}">View</a>
      </div>
    </article>

    <!-- 2) Serverless Event Signup -->
<article class="archive__item panel card--wide">
  <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/aws-serverless-signup/' | relative_url }}">
    <img src="{{ '/assets/images/serverless.png' | relative_url }}" alt="AWS Serverless Event Signup architecture">
  </a>
  <div class="card__body">
    <h3 class="archive__item-title">
      <a href="{{ '/portfolio/aws-serverless-signup/' | relative_url }}">Serverless Event Signup (AWS + Bedrock)</a>
    </h3>
    <p class="archive__item-excerpt">
      Lambda + DynamoDB + SES with an S3 front-end and API Gateway; now enhanced with AWS Bedrock (Claude 3 Haiku) for personalized, AI-generated confirmations.
    </p>
    <a class="btn btn--sm" href="{{ '/portfolio/aws-serverless-signup/' | relative_url }}">View</a>
  </div>
</article>


    <!-- 3) Custom Unix Shell -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/custom-shell/' | relative_url }}">
        <img src="{{ '/assets/images/cush.png' | relative_url }}" alt="Custom Unix Shell (C)">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/custom-shell/' | relative_url }}">Custom Unix Shell (C)</a>
        </h3>
        <p class="archive__item-excerpt">
          C-based Unix shell with parsing, pipelines, I/O redirection, job control, and robust signal handling.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/custom-shell/' | relative_url }}">View</a>
      </div>
    </article>

    <!-- 4) Personal Web & Video Server -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/personal-server/' | relative_url }}">
        <img src="{{ '/assets/images/server.png' | relative_url }}" alt="Personal Web & Video Server (C)">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/personal-server/' | relative_url }}">Personal Web &amp; Video Server (C)</a>
        </h3>
        <p class="archive__item-excerpt">
          Multithreaded HTTP/1.1 server in C: static files, JWT cookie auth, HTML5 fallback, MP4 range streaming, and IPv6 support.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/personal-server/' | relative_url }}">View</a>
      </div>
    </article>

    <!-- 5) TA Availability Kiosk (NEW) -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/ta-kiosk/' | relative_url }}">
        <img src="{{ '/assets/images/kiosk.png' | relative_url }}" alt="TA Availability Kiosk (Raspberry Pi + Flask)">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/ta-kiosk/' | relative_url }}">TA Availability Kiosk (Raspberry Pi + Flask)</a>
        </h3>
        <p class="archive__item-excerpt">
          Raspberry Pi kiosk app that shows TA schedules with search/filter, live status badges, and QR-to-email.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/ta-kiosk/' | relative_url }}">View</a>
      </div>
    </article>
  </div>
</section>

<!-- MEDIA -->
<section class="section panel section-tight" id="media">
  <div class="section-header">
    <h2>Media & Recognition</h2>
    <a class="section-link as-link" href="{{ '/media/' | relative_url }}">Show all →</a>
  </div>

  <ul class="media-list">
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/vogue.svg' | relative_url }}" alt="Teen Vogue" width="28" height="28" loading="lazy"></span>
      <div class="media-text"><strong>Teen Vogue - 21 Under 21 (2021)</strong>
        <a href="https://www.teenvogue.com/gallery/teen-vogues-21-under-21-2021" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/nbc.svg' | relative_url }}" alt="NBC News" width="28" height="28" loading="lazy"></span>
      <div class="media-text"><strong>NBC News - Leading Afghan Girls’ Robotics Team</strong>
        <a href="https://www.nbcnews.com/news/world/afghan-female-robotics-team-defiant-after-fleeing-taliban-qatar-n1277464" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/forbes.svg' | relative_url }}" alt="Forbes" width="28" height="28" loading="lazy"></span>
      <div class="media-text"><strong>Forbes - Afghan Girls Robotics Team Profile</strong>
        <a href="https://www.forbes.com/profile/afghan-girls-robotic-team/" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
    <li>
      <span class="media-icon"><img src="{{ '/assets/icons/vt.svg' | relative_url }}" alt="Virginia Tech News" width="28" height="28" loading="lazy"></span>
      <div class="media-text"><strong>Virginia Tech News - Student Spotlight (2022)</strong>
        <a href="https://news.vt.edu/articles/2022/09/ayda-haydarpour.html" target="_blank" rel="noopener">Read</a>
      </div>
    </li>
  </ul>
</section>
