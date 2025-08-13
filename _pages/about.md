---
title: "About"
permalink: /about/
layout: single
author_profile: true     # pulls name + bio from _config.yml into the sidebar
classes: wide
---

### Skills

{% if site.author.skills %}
<ul>
  {% for item in site.author.skills %}
  <li>{{ item | markdownify }}</li>
  {% endfor %}
</ul>
{% endif %}
