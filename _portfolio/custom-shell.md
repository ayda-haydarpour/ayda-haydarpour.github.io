---
title: "Custom Unix Shell (C)"
layout: single
permalink: /portfolio/custom-shell/
excerpt: "From-scratch shell with AST parsing, pipelines, I/O redirection, job control (fg/bg), and robust signal handling."
tags: [C, Systems, UNIX, POSIX, Parsing]

author_profile: false
sidebar: []

# Page hook for CSS
classes: project-page

# Thumbnail/teaser for cards
teaser: /assets/images/cush.png
---

<!-- HERO -->
<section class="project-hero">
  <div class="project-hero__inner">
    <h1 class="project-hero__title">Custom Unix Shell (C)</h1>
    <p class="project-hero__tagline">Parsing · Pipelines · Redirection · Job Control · Signals</p>

    <p class="project-hero__intro">
      A minimal Unix shell in <strong>C</strong> that parses commands into an AST, builds <strong>pipelines</strong>,
      wires <strong>I/O redirection</strong>, and manages foreground/background <strong>jobs</strong> with correct signal handling.
      Children are launched with <code>posix_spawnp</code>, placed into a process group, and synchronized via a
      <code>SIGCHLD</code> handler and <code>waitpid</code>. Foreground control is transferred with <code>tcsetpgrp</code> and
      restored safely.
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
        <p>C (POSIX); <code>posix_spawnp</code>, <code>pipe</code>, <code>dup2</code>, <code>setpgid</code>/<code>tcsetpgrp</code>, <code>waitpid</code>, <code>termios</code>, <code>readline</code>/history</p>
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
        <p>Reliable pipelines and job control; stable under <code>Ctrl-C</code>/<code>Ctrl-Z</code> with no zombies</p>
      </div>
    </div>

  </div>
</section>

<!-- GOALS -->
<section class="section-card">
  <h2>Goals</h2>
  <ul>
    <li>Implement a usable shell that supports pipelines and file-descriptor redirection (<code>&lt;</code>, <code>&gt;</code>, <code>&gt;&gt;</code>, stderr routing).</li>
    <li>Handle UNIX job control (foreground/background) and signals correctly (<code>SIGINT</code>, <code>SIGTSTP</code>, <code>SIGCHLD</code>).</li>
    <li>Provide core built-ins and history expansion.</li>
    <li>Maintain safety: close unused FDs (<code>O_CLOEXEC</code>), prevent zombies, and report errors clearly.</li>
  </ul>
</section>

<!-- EXECUTION FLOW -->
<section class="section-card">
  <h2>Execution Flow</h2>
  <figure class="figure">
    <img src="{{ '/assets/images/cush.png' | relative_url }}" alt="Custom Shell terminal screenshot">
    <figcaption>Tokenizer &amp; parser build an AST; executor sets up pipes/redirection; jobs run in FG/BG with proper signal handling; job table stays in sync via <code>SIGCHLD</code>.</figcaption>
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
    <li><strong>Pipelines:</strong> build <em>n−1</em> pipes; connect stdout/stdin across children.</li>
    <li><strong>Redirection:</strong> <code>&lt;</code>, <code>&gt;</code>, <code>&gt;&gt;</code>, optional stderr→stdout via <code>dup2</code>; close unused FDs.</li>
    <li><strong>Jobs:</strong> track process groups; supports <code>jobs</code>, <code>fg</code>, <code>bg</code>, <code>stop</code>, <code>kill</code>, plus built-ins <code>cd</code> and <code>exit</code>; <code>history</code> via readline.</li>
    <li><strong>Signals:</strong> deliver <code>Ctrl-C</code>/<code>Ctrl-Z</code> to the foreground process group; reap children with <code>waitpid()</code> in a <code>SIGCHLD</code> handler.</li>
  </ul>
</section>

<!-- RESULTS -->
<section class="section-card">
  <h2>Results</h2>
  <ul>
    <li>Correct pipeline behavior and exit-status propagation.</li>
    <li>No zombie processes; resilient under repeated interrupts/suspends.</li>
    <li>Consistent resource hygiene and clear error paths.</li>
  </ul>
</section>

<!-- DEMO -->
<section class="section-card">
  <h2>Demo</h2>
  {% comment %} Replace VIDEO_ID when you upload a short terminal walkthrough {% endcomment %}
  {% include video id="VIDEO_ID" provider="youtube" %}
</section>
