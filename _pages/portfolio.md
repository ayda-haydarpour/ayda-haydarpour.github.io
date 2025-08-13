---
title: "Projects"
layout: single
permalink: /portfolio/
author_profile: true
sidebar:
  - title: "Skills"
    text: |
      - **Cloud Services:** AWS (EC2, S3, RDS, VPC, Route 53, CloudFront, IAM, CloudWatch, Auto Scaling, Load Balancing)
      - **Security & Networking:** IAM policies & access control, network security, VPNs & firewalls, data encryption & hashing, monitoring & logging, Security+ best practices
      - **Programming & Scripting:** Python, Java, C, Bash, JavaScript, HTML/CSS, SQL
      - **Tools & Platforms:** Linux, Git & GitHub, Wireshark, system monitoring tools
  - title: "Contact"
    text: |
      - **Email:** [aydahaydarpour@gmail.com](mailto:aydahaydarpour@gmail.com)
      - **GitHub:** [ayda-hdp](https://github.com/ayda-hdp)
---

<div class="panel" style="margin-bottom:1rem;">
  <strong>Featured Project</strong>
</div>

<div class="feature__wrapper">
  <div class="feature__item">
    <div class="archive__item panel">
      <a class="archive__item-teaser" href="{{ '/portfolio/aws-multi-region-resume/' | relative_url }}">
        <img class="teaser--ratio" src="{{ '/assets/images/diagram.png' | relative_url }}" alt="AWS Multi-Region Resume architecture">
      </a>
      <h2 class="archive__item-title">
        <a href="{{ '/portfolio/aws-multi-region-resume/' | relative_url }}">AWS Multi-Region Resume Site</a>
      </h2>
      <div class="tags">
        <span class="tag">AWS</span><span class="tag">CloudFront</span><span class="tag">Security</span>
      </div>
      <p class="archive__item-excerpt">Secure, globally distributed static site with failover, access control, and CI/CD.</p>
      <p><a class="btn btn--primary" href="{{ '/portfolio/aws-multi-region-resume/' | relative_url }}">View</a></p>
    </div>
  </div>
</div>

## All Projects

{%- assign items = site.portfolio | sort: 'date' | reverse -%}
<div class="entries-grid">
{%- for item in items -%}
  <article class="archive__item panel" style="padding:0;">
    {% if item.teaser %}
    <a class="archive__item-teaser" href="{{ item.url | relative_url }}">
      <img class="teaser--ratio" src="{{ item.teaser | relative_url }}" alt="">
    </a>
    {% endif %}
    <div style="padding:1rem;">
      <h2 class="archive__item-title" style="margin-top:0;">
        <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
      </h2>

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
