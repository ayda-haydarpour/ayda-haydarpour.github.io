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

# Single featured card (your current project)
feature_row:
  - image_path: /assets/images/secure-resume-arch.png   # <-- put your diagram here
    alt: "AWS Multi-Region Resume architecture"
    title: "AWS Multi-Region Resume Site"
    excerpt: "Secure, globally distributed static site with failover, access control, and CI/CD."
    url: "{{ '/portfolio/aws-multi-region-resume/' | relative_url }}"   # <-- slug comes from your file name in _portfolio/
    btn_label: "View"
    btn_class: "btn--primary"
---

{% include feature_row %}

## All Projects

{% include collection
   collection="portfolio"
   sort_by="date"
   sort_order="reverse"
   entries_layout="list" %}
