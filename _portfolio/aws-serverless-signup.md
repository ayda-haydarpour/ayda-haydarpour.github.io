---
title: "Serverless Event Signup (AWS)"
layout: single
permalink: /portfolio/aws-serverless-signup/
excerpt: "Lambda + DynamoDB + SES with an S3 front-end via API Gateway, least-privilege IAM, and CloudWatch logging."
tags: [AWS, Lambda, DynamoDB, SES, API Gateway, S3]

author_profile: false
sidebar: []

classes: project-page
teaser: /assets/images/serverless.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">Serverless Event Signup</h1>
    <p class="project-hero__tagline">Serverless data capture · Email confirmation · Least-privilege IAM</p>

    <p class="project-hero__intro">
      A lean, serverless signup flow: API Gateway (HTTP) triggers Lambda to store registrations in DynamoDB and email confirmations via SES. The front end runs on S3, with CORS enabled, environment-based configuration, and CloudWatch logging.
    </p>
  </div>
</section>


<!-- QUICK FACTS -->
<section class="facts">
  <div class="facts-grid">

    <!-- Stack -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/briefcase.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Stack</h3>
        <p>API Gateway (HTTP API), Lambda (Python 3.11), DynamoDB, SES, S3, CloudWatch</p>
      </div>
    </div>

    <!-- Focus -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/shield-check.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Focus</h3>
        <p>Least-privilege IAM, input validation, CORS, cost-efficient serverless</p>
      </div>
    </div>

    <!-- Outcome -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/rocket.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>One-click signup with email confirmation, durable writes, and clear observability</p>
      </div>
    </div>

  </div>
</section>

<!-- GOALS -->
<section class="section-card">
  <h2>Goals</h2>
  <ul>
    <li>Capture registrations via a simple, secure front-end.</li>
    <li>Write each registration to DynamoDB with a unique ID and timestamp.</li>
    <li>Send a confirmation email using Amazon SES.</li>
    <li>Keep permissions tight with a dedicated Lambda execution role.</li>
    <li>Enable easy hosting (S3) and clean CORS for browser calls.</li>
  </ul>
</section>

<!-- ARCHITECTURE -->
<section class="section-card">
  <h2>Architecture</h2>
  <figure class="figure figure--dark">
    <img src="{{ '/assets/images/serverless.png' | relative_url }}" alt="Serverless Event Signup architecture diagram">
    <figcaption>
      Browser → API Gateway → Lambda → DynamoDB (write), SES (email), CloudWatch (logs). Static front-end on S3.
    </figcaption>
  </figure>

  <div class="callout callout--info">
    <strong>Why this design?</strong> It’s fully managed, low-cost, and scales automatically. IAM is scoped to logs, a single DynamoDB table, and one SES identity. 
    API Gateway provides CORS and a minimal proxy to Lambda.
  </div>
</section>

<!-- HOW IT'S BUILT -->
<section class="section-card">
  <h2>How it’s built</h2>

  <div class="stack-badges">
    <span>API Gateway (HTTP API)</span>
    <span>Lambda (Python 3.11)</span>
    <span>DynamoDB</span>
    <span>Amazon SES</span>
    <span>S3 (static site)</span>
    <span>CloudWatch</span>
  </div>

  <h3>Key steps</h3>
  <ol>
    <li><strong>DynamoDB:</strong> Create table <code>EventRegistrations</code> with partition key <code>id</code> (String), on-demand capacity.</li>
    <li><strong>SES:</strong> Verify the “From” email (and the “To” email in sandbox).</li>
    <li><strong>IAM:</strong> Create execution role <code>lambda-serverless-signup-exec</code> with inline policy for CloudWatch logs, <code>dynamodb:PutItem</code> on the table, and <code>ses:SendEmail</code> on the identity.</li>
    <li><strong>Lambda:</strong> Python 3.11 function <code>submitRegistration</code> with env vars <code>TABLE_NAME</code>, <code>FROM_EMAIL</code>, <code>SES_REGION</code>. Validates inputs, writes to DynamoDB, sends email via SES, returns JSON with CORS headers.</li>
    <li><strong>API Gateway:</strong> HTTP API with route <code>POST /register</code>, Lambda proxy integration, and CORS for <code>POST, OPTIONS</code>.</li>
    <li><strong>Front-end:</strong> S3 static site hosting with <code>index.html</code> form that <code>fetch()</code>es the API.</li>
  </ol>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li><strong>Email confirmations</strong> delivered by SES (sandbox-safe).</li>
    <li><strong>Durable writes</strong> in DynamoDB with UUID and timestamps.</li>
    <li><strong>Operational visibility</strong> via CloudWatch logs (7-day retention).</li>
    <li><strong>Low cost</strong> using serverless and on-demand capacity.</li>
    <li><strong>Security first:</strong> IAM least-privilege and CORS.</li>
  </ul>
</section>

<!-- DEMO -->
<section class="section-card">
  <h2>Demo</h2>
  {% include video id="zhtm_V9lOd0" provider="youtube" %}
</section>




