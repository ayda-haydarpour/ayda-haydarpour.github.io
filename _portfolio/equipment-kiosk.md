---
title: "Equipment Checkout Kiosk (Web + Google Sheets)"
layout: single
permalink: /portfolio/equipment-kiosk/
excerpt: "Interactive equipment checkout kiosk with live availability, modal checkout, QR instructions, and Google Sheets–backed inventory."
tags:
  - JavaScript
  - Frontend
  - Kiosk
  - Inventory Systems
  - Google Sheets
  - UX
  - Automation
  - Web Apps

author_profile: false
sidebar: []

# Page hook for CSS
classes: project-page

# Thumbnail / teaser image
teaser: /assets/images/equipment-kiosk.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">Equipment Checkout Kiosk</h1>
    <p class="project-hero__tagline">
      Vanilla JS · Modal UI · Live Inventory · QR Instructions · Google Sheets Backend
    </p>

    <p class="project-hero__intro">
      A self-serve <strong>equipment checkout kiosk</strong> built for shared studio and maker spaces.
      Users can browse available kits, view real-time availability, scan QR-based instructions,
      and check out items through a streamlined interface—while all inventory and loan data
      is tracked automatically using <strong>Google Sheets</strong>.
    </p>
  </div>
</section>

<!-- QUICK FACTS -->
<section class="facts">
  <div class="facts-grid">

    <div class="fact-card">
      <h3>Stack</h3>
      <p>HTML, CSS, Vanilla JavaScript, Google Sheets (CSV export), Google Forms</p>
    </div>

    <div class="fact-card">
      <h3>Focus</h3>
      <p>Kiosk UX, frontend systems design, data synchronization, client-side logic</p>
    </div>

    <div class="fact-card">
      <h3>Outcome</h3>
      <p>Reliable zero-backend inventory kiosk with live availability and QR-driven instructions</p>
    </div>

  </div>
</section>

---

## Problem

Shared creative spaces often rely on **manual sign-out sheets** or staff intervention to manage
equipment usage. This leads to:

- Unclear availability  
- Lost or unreturned items  
- No real-time inventory visibility  
- High operational overhead for staff  

---

## Solution

This project replaces manual workflows with a **web-based kiosk system** that:

- Displays all equipment kits in a responsive grid  
- Computes availability in real time  
- Prevents checkout when inventory is depleted  
- Logs usage automatically without requiring authentication  
- Requires **no custom backend server**  

---

## Core Features

### 🔍 Search & Filtering
- Live text search across:
  - Kit name
  - Category
  - Description
  - Tags
  - Location
- Category dropdown populated dynamically from data
- Inactive kits automatically hidden

---

### 📦 Live Availability Tracking

Availability is computed client-side as:

```text
available = total quantity − active loans
