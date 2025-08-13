---
title: "AWS Multi-Region Resume Site"
layout: single
permalink: /portfolio/aws-multi-region-resume/
excerpt: "Secure, globally distributed static site with failover, access control, and CI/CD."
date: 2025-08-01
tags: [AWS, Security, CloudFront, S3, OAC, CI/CD]

# Show the left sidebar profile on this page
author_profile: true

# Improve navigation/readability
toc: true
toc_sticky: true

# Override collection default (“wide”) to a normal reading width
classes: ""

# Keep a teaser for cards, but no giant header hero
teaser: /assets/images/diagram.png
---

> A static resume site with **secure access control**, **multi-region failover**, and **automated deployments** from GitHub.

---

## Demo (YouTube)
{% include video id="60pCkb77k8s" provider="youtube" %}

---

## Goals
- Host a static site securely without making S3 buckets public.
- Deliver globally with low latency using CloudFront.
- Set up failover between two AWS regions.
- Automate deployments from GitHub.

---

## Architecture (overview)

![Architecture Diagram]({{ '/assets/images/diagram.png' | relative_url }}){: .align-center width="760" }

{:.notice--info}
**Why this design?** CloudFront + OAC keeps S3 private, origin groups enable regional failover, and GitHub Actions push to both regions then invalidate the CDN for near-instant updates.

---

## How it’s built

{:.notice--primary}
**Stack:** CloudFront (OAC, origin groups) · S3 (private) · IAM · Route 53 · GitHub Actions

**S3 Buckets**  
- Two **private** buckets:
  - `ayda-resume-us-east-1` (primary)
  - `ayda-resume-eu-west-1` (secondary)
- Store `index.html`, `style.css`, and `resume.pdf`.

**CloudFront**  
- **Origin Access Control (OAC)** so S3 stays private.  
- **Origin group** with failover (primary us-east-1, secondary eu-west-1).  
- Forces **HTTPS**; default root object = `index.html`.

**Security**  
- Bucket policies allow only CloudFront (via OAC).  
- No public S3 access. Optionally add WAF for extra hardening.

**CI/CD**  
- GitHub Actions:
  1. Sync files to both S3 buckets.
  2. Invalidate CloudFront so updates go live immediately.

---

## Results
- **Private-by-default hosting** with CDN performance.  
- **Regional resilience** (automatic failover).  
- **Fast releases** via CI/CD and cache invalidation.

---

## Links
- **Repo:** <https://github.com/ayda-hdp/secure-resume-delivery>  
- **Live demo:** https://\<your-cloudfront-domain\>
