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

# Featured card (left sidebar stays visible)
feature_row:
  - image_path: /assets/images/secure-resume-arch.png
    alt: "AWS Multi-Region Resume architecture"
    title: "AWS Multi-Region Resume Site"
    excerpt: "Secure, globally distributed static site with failover, access control, and CI/CD."
    # Use the SAME path as the project's permalink above (project site needs baseurl at runtime)
    url: "/portfolio/aws-multi-region-resume/"
    btn_label: "View"
    btn_class: "btn--primary"
---

{% include feature_row %}

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
