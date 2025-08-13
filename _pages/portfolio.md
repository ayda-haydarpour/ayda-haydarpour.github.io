---
title: "Projects"
layout: single
permalink: /portfolio/
classes: wide

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

<div class="notice--primary" style="margin-bottom:1.25rem;"><strong>Featured Project</strong></div>

<div class="feature__wrapper">
  <div class="feature__item">
    <div class="archive__item">
      <div class="archive__item-teaser">
        <img src="{{ '/assets/images/diagram.png' | relative_url }}" alt="AWS Multi-Region Resume architecture">
      </div>
      <h2 class="archive__item-title">AWS Multi-Region Resume Site</h2>
      <p class="archive__item-excerpt">Secure, globally distributed static site with failover, access control, and CI/CD.</p>
      <p>
        <a class="btn btn--primary" href="{{ '/portfolio/aws-multi-region-resume/' | relative_url }}">View</a>
      </p>
    </div>
  </div>
</div>

## All Projects

{%- assign items = site.portfolio | sort: 'date' | reverse -%}
<div class="entries-list">
{%- for item in items -%}
  <article class="archive__item">
    <h2 class="archive__item-title">
      <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
    </h2>

    {%- if item.teaser -%}
    <div class="archive__item-teaser">
      <img src="{{ item.teaser | relative_url }}" alt="">
    </div>
    {%- endif -%}

    {%- if item.excerpt -%}
    <p class="archive__item-excerpt">
      {{ item.excerpt | markdownify | strip_html | truncate: 180 }}
    </p>
    {%- endif -%}
  </article>
{%- endfor -%}
</div>
