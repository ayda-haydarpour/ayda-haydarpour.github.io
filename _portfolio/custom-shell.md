---
title: "Custom Unix Shell (C)"
layout: single
permalink: /portfolio/custom-shell/
excerpt: "A from-scratch shell with parsing, pipelines, redirection, job control, and robust signal handling."
tags: [C, Systems, UNIX, Security, Parsing]

author_profile: false
sidebar: []

# Page hook for CSS
classes: project-page

# Thumbnail/teaser for cards
teaser: /assets/images/custom-shell.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">Custom Unix Shell (C)</h1>
    <p class="project-hero__tagline">Parsing · Pipelines · Redirection · Job Control · Signals</p>

    <p class="project-hero__intro">
    A minimal Unix shell written in <strong>C</strong> with a real tokenizer/parser, support for
    <strong>pipelines</strong> and <strong>I/O redirection</strong>, foreground/background <strong>job control</strong>,
    and robust <strong>signal handling</strong>.
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
        <p>C (POSIX), fork/exec, pipe, dup2, waitpid, termios, signal handlers</p>
      </div>
    </div>

    <!-- Focus -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/shield-check.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Focus</h3>
        <p>Input parsing, process control, safe execution, robust error handling</p>
      </div>
    </div>

    <!-- Outcome -->
    <div class="fact-card">
      <div class="fact-icon" aria-hidden="true">
        <img src="{{ '/assets/icons/rocket.svg' | relative_url }}" alt="">
      </div>
      <div class="fact-content">
        <h3>Outcome</h3>
        <p>Reliable shell behavior with pipelines and jobs; stable under signals</p>
      </div>
    </div>

  </div>
</section>

<!-- GOALS -->
<section class="section-card">
  <h2>Goals</h2>
  <ul>
    <li>Implement a usable shell that supports pipelines and file descriptor redirection.</li>
    <li>Handle UNIX job control (foreground/background) and signals correctly.</li>
    <li>Provide core built-ins and environment variable expansion.</li>
    <li>Maintain safety: close unused FDs, prevent zombies, and report errors clearly.</li>
  </ul>
</section>

<!-- EXECUTION FLOW -->
<section class="section-card">
  <h2>Execution Flow</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/custom-shell.png' | relative_url }}" alt="Custom Shell terminal screenshot">
    <figcaption>Tokenizer &amp; parser build an AST; executor sets up pipes and redirection; jobs run in foreground/background with proper signal handling.</figcaption>
  </figure>
</section>

<!-- HOW IT'S BUILT -->
<section class="section-card">
  <h2>How it’s built</h2>

  <div class="stack-badges">
    <span>Tokenizer &amp; Parser</span>
    <span>AST Execution</span>
    <span>Pipes &amp; Redirection</span>
    <span>Job Control</span>
    <span>Signals</span>
  </div>

  <h3>Key behaviors</h3>
  <ul>
    <li><strong>Pipelines:</strong> constructs pipe chains and connects stdout/stdin across children.</li>
    <li><strong>Redirection:</strong> sets up <code>dup2()</code> for <code>&gt;</code>, <code>&lt;</code>, and stderr routing.</li>
    <li><strong>Jobs:</strong> tracks process groups; supports <code>fg</code>/<code>bg</code> and a <code>jobs</code> listing.</li>
    <li><strong>Signals:</strong> delivers Ctrl-C/Z correctly; reaps children with <code>waitpid()</code>.</li>
    <li><strong>Built-ins:</strong> <code>cd</code>, <code>exit</code>, <code>export</code>/<code>unset</code>, <code>jobs</code>, <code>fg</code>, <code>bg</code>.</li>
  </ul>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li>Correct pipeline behavior and exit status propagation.</li>
    <li>Stable under signal storms (Ctrl-C / Ctrl-Z) with no zombie processes.</li>
    <li>Resource hygiene: closes unused file descriptors; consistent error paths.</li>
  </ul>
</section>

<!-- DEMO -->
<section class="section-card">
  <h2>Demo</h2>
  {% comment %} Replace VIDEO_ID when you upload a short terminal walkthrough {% endcomment %}
  {% include video id="VIDEO_ID" provider="youtube" %}
</section>
