---
title: "Projects"
layout: single
permalink: /portfolio/
classes: wide

# Featured cards at the top
feature_row:
  - image_path: /assets/images/diagram.png
    alt: "AWS Multi-Region Resume architecture"
    title: "AWS Multi-Region Resume Site"
    excerpt: "Secure, globally distributed static site with failover, access control, and CI/CD."
    url: "{{ '/portfolio/aws-multi-region-resume/' | relative_url }}"
    btn_label: "View"
    btn_class: "btn--primary"

  - image_path: /assets/images/coming-soon.png
    alt: "Custom Shell"
    title: "Custom Shell (C, POSIX)"
    excerpt: "Systems programming project — process control, piping, and APIs. Write-up coming soon."
    url: "{{ '/portfolio/custom-shell/' | relative_url }}"
    btn_label: "Coming soon"

  - image_path: /assets/images/coming-soon.png
    alt: "TA Kiosk"
    title: "TA Availability Kiosk (Raspberry Pi)"
    excerpt: "Networking + SSH + Wi-Fi config, frontend for lab availability. Write-up coming soon."
    url: "{{ '/portfolio/ta-kiosk/' | relative_url }}"
    btn_label: "Coming soon"
---

{% include feature_row %}

## All Projects

{% include collection
   collection="portfolio"
   sort_by="date"
   sort_order="reverse"
   entries_layout="grid" %}
