---
title: "Custom Unix Shell (C)"
layout: single
permalink: /portfolio/custom-shell/
excerpt: "A from-scratch shell with parsing, pipelines, redirection, job control, and robust signal handling."
tags: [C, Systems, UNIX, Security, Parsing, Docker]

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
    A minimal Unix shell written in <strong>C</strong> with a real tokenizer/parser, support for
    <strong>pipelines</strong> and <strong>I/O redirection</strong>, foreground/background <strong>job control</strong>,
    and robust <strong>signal handling</strong>.  
    To make it portable, I containerized the shell environment using <strong>Docker</strong>, so it can be easily built and tested across systems.
    </p>
  </div>
</section>

<!-- STACK -->
<div class="project-stack">
  <h3>Stack</h3>
  <p>C (POSIX); <code>posix_spawnp</code>, <code>pipe</code>, <code>dup2</code>, <code>setpgid</code>/<code>tcsetpgrp</code>, 
  <code>waitpid</code>, <code>termios</code>, <code>readline</code>/history, Docker for containerized builds</p>
</div>

<!-- DEMO -->
<div class="project-demo">
  <h3>Demo</h3>
  <p>Here’s a sample Docker run showing the shell environment in action:</p>
  <img src="/assets/images/docker-demo.png" alt="Docker run demo screenshot" />
  <p>
    You can also watch a short demo video here:  
    <a href="https://youtu.be/LHpC18NpsEU" target="_blank">Watch on YouTube</a>
  </p>
</div>
