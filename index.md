---
layout: single
title: "Portfolio"
permalink: /portfolio/
author_profile: false
classes: wide
---

<section class="page__content" itemprop="text">

  <h1 class="page__title">Portfolio</h1>

  <div class="entries-grid entries-grid--wide">

    <!-- Custom Unix Shell -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/custom-shell/' | relative_url }}">
        <img src="{{ '/assets/images/cush.png' | relative_url }}" alt="Custom Unix Shell (C)">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/custom-shell/' | relative_url }}">Custom Unix Shell (C)</a>
        </h3>
        <p class="archive__item-excerpt">
          From-scratch shell with parsing, pipelines, redirection, job control, and robust signal handling.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/custom-shell/' | relative_url }}">View</a>
      </div>
    </article>

    <!-- Personal Web & Video Server -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/personal-server/' | relative_url }}">
        <img src="{{ '/assets/images/server.png' | relative_url }}" alt="Personal Web & Video Server (C)">
      </a>
      <div class="card__body">
        <h3 class="archive__item-title">
          <a href="{{ '/portfolio/personal-server/' | relative_url }}">Personal Web &amp; Video Server (C)</a>
        </h3>
        <p class="archive__item-excerpt">
          Multithreaded HTTP/1.1 server with static files, JWT authentication, MP4 streaming, and IPv6.
        </p>
        <a class="btn btn--sm" href="{{ '/portfolio/personal-server/' | relative_url }}">View</a>
      </div>
    </article>

    <!-- TA Availability Kiosk (NEW) -->
    <article class="archive__item panel card--wide">
      <a class="archive__item-teaser teaser--wide" href="{{ '/portfolio/ta-kiosk/' | relative_url }}">
        <img src="{{ '/assets/images/ta-kiosk.png' | relative_url }}" alt="TA Availability Kiosk (Raspberry Pi + Flask)">
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
