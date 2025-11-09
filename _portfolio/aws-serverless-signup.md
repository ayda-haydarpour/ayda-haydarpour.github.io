---
title: "Serverless Event Signup (AWS + Bedrock)"
layout: single
permalink: /portfolio/aws-serverless-signup/
excerpt: "Lambda + DynamoDB + SES with an S3 front-end via API Gateway, Bedrock (Claude 3 Haiku) integration, and CloudWatch logging."
tags: [AWS, Lambda, DynamoDB, SES, API Gateway, S3, Bedrock, GenAI]

author_profile: false
sidebar: []

classes: project-page
teaser: /assets/images/serverless.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">Serverless Event Signup (with AWS Bedrock)</h1>
    <p class="project-hero__tagline">Serverless data capture · Email confirmation · AI-powered message generation</p>

    <p class="project-hero__intro">
      A lean, serverless signup flow: API Gateway (HTTP) triggers Lambda to store registrations in DynamoDB and email confirmations via SES. 
      The front end runs on S3 with CORS enabled, environment-based configuration, and CloudWatch logging. 
      <!-- NEW -->
      A later phase introduced AWS Bedrock and Claude 3 Haiku for personalized confirmation messages, showcasing how GenAI can enhance user communication in a fully serverless architecture.
    </p>
  </div>
</section>


<!-- QUICK FACTS -->
<section class="facts">
  <div class="facts-grid">

    <div class="fact-card">
      <div class="fact-icon"><img src="{{ '/assets/icons/briefcase.svg' | relative_url }}" alt=""></div>
      <div class="fact-content">
        <h3>Stack</h3>
        <p>API Gateway (HTTP API), Lambda (Python 3.11), DynamoDB, SES, S3, CloudWatch, Bedrock (Claude 3 Haiku)</p>
      </div>
    </div>

    <div class="fact-card">
      <div class="fact-icon"><img src="{{ '/assets/icons/shield-check.svg' | relative_url }}" alt=""></div>
      <div class="fact-content">
        <h3>Focus</h3>
        <p>Least-privilege IAM, input validation, cost-efficient serverless, prompt engineering with Bedrock</p>
      </div>
    </div>

    <div class="fact-card">
      <div class="fact-icon"><img src="{{ '/assets/icons/rocket.svg' | relative_url }}" alt=""></div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>One-click signup with dynamic, AI-generated confirmations and full observability</p>
      </div>
    </div>

  </div>
</section>

<!-- GOALS -->
<section class="section-card">
  <h2>Goals</h2>
  <ul>
    <li>Capture event registrations via a secure, serverless front-end.</li>
    <li>Write each registration to DynamoDB with a unique ID and timestamp.</li>
    <li>Send confirmation emails through SES.</li>
    <li><!-- NEW -->Experiment with generative AI using AWS Bedrock (Claude 3 Haiku) to tailor confirmation messages based on registration data.</li>
    <li>Maintain least-privilege IAM and minimal operational overhead.</li>
  </ul>
</section>

<!-- ARCHITECTURE -->
<section class="section-card">
  <h2>Architecture</h2>
  <figure class="figure figure--dark">
    <img src="{{ '/assets/images/serverless.png' | relative_url }}" alt="Serverless Event Signup architecture diagram">
    <figcaption>
      Browser → API Gateway → Lambda → DynamoDB (write), SES (email), Bedrock (AI text), CloudWatch (logs). Static front-end on S3.
    </figcaption>
  </figure>

  <div class="callout callout--info">
    <strong>Why this design?</strong> It’s fully managed, low-cost, and now enhanced with Bedrock for AI-driven personalization. 
    IAM is scoped to logs, DynamoDB, SES, and a restricted Bedrock invocation policy.
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
    <span>Amazon Bedrock</span>
    <span>S3 (static site)</span>
    <span>CloudWatch</span>
  </div>

  <h3>Key steps</h3>
  <ol>
    <li><strong>DynamoDB:</strong> Table <code>EventRegistrations</code> with partition key <code>id</code> (String).</li>
    <li><strong>SES:</strong> Verified identities for sending sandbox-safe confirmations.</li>
    <li><strong>Lambda:</strong> Python 3.11 function <code>submitRegistration</code> validates input, writes to DynamoDB, 
        generates an AI-personalized email body by invoking Bedrock (Claude 3 Haiku), and sends via SES.</li>
    <li><strong>API Gateway:</strong> Route <code>POST /register</code> (Lambda proxy integration) with CORS for <code>POST, OPTIONS</code>.</li>
    <li><strong>Front-end:</strong> S3 static site with form submission using <code>fetch()</code> to the API.</li>
    <li><strong>Monitoring:</strong> CloudWatch logs and metrics for both Lambda execution and Bedrock inference time.</li>
  </ol>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li><strong>Email confirmations</strong> now feature AI-generated, context-aware text using Bedrock.</li>
    <li><strong>Durable writes</strong> in DynamoDB with UUID + timestamps.</li>
    <li><strong>Visibility</strong> via CloudWatch logs and metrics.</li>
    <li><strong>Low cost</strong> due to on-demand serverless stack.</li>
    <li><strong>Security first:</strong> Scoped IAM, sanitized inputs, and CORS.</li>
  </ul>
</section>

<!-- DEMO -->
<section class="section-card">
  <h2>Demo</h2>
  {% include video id="zhtm_V9lOd0" provider="youtube" %}
</section>
