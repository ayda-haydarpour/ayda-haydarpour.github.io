---
title: "AWS Multi-Region Resume Site"
excerpt: "Secure, globally distributed static site with failover, access control, and CI/CD."
date: 2025-08-01
tags: [AWS, Security, CloudFront, S3, OAC, CI/CD]

# 🔒 Fix the 404: publish this page at a stable path
permalink: /portfolio/aws-multi-region-resume/

# Card + header images
header:
  image: /assets/images/diagram.png
  image_description: "Architecture diagram"
teaser: /assets/images/diagram.png
---

This project delivers a **static resume site** with **secure access control**, **multi-region failover**, and **automated deployments** from GitHub.

---

## Goals
- Host a static site securely without making S3 buckets public.
- Deliver globally with low latency using CloudFront.
- Set up failover between two AWS regions.
- Automate deployments from GitHub.

---

## How it’s built

**S3 Buckets**  
- Two **private** buckets:
  - `ayda-resume-us-east-1` (primary)
  - `ayda-resume-eu-west-1` (secondary)
- Store `index.html`, `style.css`, and a PDF resume.

**CloudFront**  
- **Origin Access Control (OAC)** keeps S3 private.
- **Origin group** with failover (primary us-east-1, secondary eu-west-1).
- Forces **HTTPS**; default root object = `index.html`.

**Security**  
- Bucket policies allow only CloudFront (via OAC).
- No public S3 access.

**CI/CD**  
- GitHub Actions:
  1. Syncs files to both S3 buckets.
  2. Invalidates CloudFront so updates go live immediately.

---

## Architecture
![Architecture Diagram]({{ '/assets/images/diagram.png' | relative_url }})

---

## Links
- **Live demo:** https://<your-cloudfront-domain>
