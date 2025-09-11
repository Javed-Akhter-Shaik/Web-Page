---
layout: page
title: "VR Portfolio"
permalink: /vr-portfolio/
---

<style>
/* General Styling */
body {
  margin: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(to bottom, #1b2735, #090a0f);
  color: #fff;
  text-align: center;
}

/* Navigation Bar */
nav {
  display: flex;
  justify-content: center;
  gap: 50px;
  padding: 20px;
  background: rgba(0,0,0,0.6);
  border-radius: 12px;
  width: fit-content;
  margin: auto;
}
nav a {
  color: #eee;
  text-decoration: none;
  font-weight: bold;
  font-size: 18px;
  transition: 0.3s;
}
nav a:hover {
  color: #00e0ff;
}

/* Hero Section */
.hero {
  padding: 60px 20px;
}
.hero h1 {
  font-size: 3em;
  margin-bottom: 10px;
}
.hero p {
  font-size: 1.2em;
  color: #ccc;
}

/* Portfolio Grid */
.portfolio {
  padding: 40px 20px;
}
.portfolio h2 {
  font-size: 2em;
  margin-bottom: 30px;
}
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 25px;
}
.card {
  background: #111827;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0,0,0,0.4);
  cursor: pointer;
  transition: transform 0.3s ease;
}
.card:hover {
  transform: translateY(-8px);
}
.card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}
.card h3 {
  margin: 12px 0;
}
.card p {
  font-size: 0.9em;
  padding: 0 15px 15px;
  color: #aaa;
}

/* Video Section */
.video-section {
  display: none;
  margin-top: 60px;
  padding: 20px;
}
.video-section iframe {
  width: 80%;
  max-width: 800px;
  height: 450px;
  border-radius: 10px;
  margin-bottom: 20px;
}
.video-section p {
  max-width: 800px;
  margin: auto;
  text-align: left;
  line-height: 1.6;
}
</style>

<!-- Navigation -->
<nav>
  <a href="#portfolio">Portfolio</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>

<!-- Hero Section -->
<section class="hero">
  <h1>Hi, I am Javed</h1>
  <p>XR Developer – VR/AR Prototyper – AI-driven Robotics</p>
</section>

<!-- Portfolio Section -->
<section id="portfolio" class="portfolio">
  <h2>Portfolio</h2>
  <div class="grid">

    <!-- Project 1 -->
    <div class="card" onclick="showVideo('video1')">
      <img src="/assets/images/gearbox.png" alt="Gearbox VR">
      <h3>Interactive Gear Box Assembly</h3>
      <p>Step-by-step immersive VR guide for gearbox assembly.</p>
    </div>

    <!-- Project 2 -->
    <div class="card" onclick="showVideo('video2')">
      <img src="/assets/images/inspection.png" alt="Inspection VR">
      <h3>Inspection of Mechanical Components</h3>
      <p>Compare master and target models in real-time.</p>
    </div>

    <!-- Project 3 -->
    <div class="card" onclick="showVideo('video3')">
      <img src="/assets/images/measurement.png" alt="Measurement VR">
      <h3>Real-time Measurement</h3>
      <p>Interact with components and measure dynamically.</p>
    </div>

    <!-- Project 4 -->
    <div class="card" onclick="showVideo('video4')">
      <img src="/assets/images/npc.png" alt="NPC VR">
      <h3>Smart NPC in VR</h3>
      <p>Voice-driven dialogue with intelligent virtual characters.</p>
    </div>

    <!-- Project 5 -->
    <div class="card" onclick="showVideo('video5')">
      <img src="/assets/images/tabletennis.png" alt="Table Tennis VR">
      <h3>VR Table Tennis</h3>
      <p>Physics-accurate, immersive VR table tennis experience.</p>
    </div>

    <!-- Project 6 -->
    <div class="card" onclick="showVideo('video6')">
      <img src="/assets/images/gorilla.png" alt="Gorilla VR">
      <h3>Gorilla vs 100 Men</h3>
      <p>Action-packed VR game with physics-based combat.</p>
    </div>
  </div>
</section>

<!-- Video Sections -->
<div id="video1" class="video-section">
  <iframe src="https://www.youtube.com/embed/UaA2s17bcwA" frameborder="0" allowfullscreen></iframe>
  <p><b>Interactive Gear Box Assembly:</b> An immersive guide for assembling mechanical gearboxes with XR Toolkit.</p>
</div>

<div id="video2" class="video-section">
  <iframe src="https://www.youtube.com/embed/sI5wcQxgHYk" frameborder="0" allowfullscreen></iframe>
  <p><b>Inspection of Mechanical Components:</b> Real-time comparison of models, with automatic error detection.</p>
</div>

<div id="video3" class="video-section">
  <iframe src="https://www.youtube.com/embed/ggCbe4o8uC0" frameborder="0" allowfullscreen></iframe>
  <p><b>Real-time Measurement:</b> VR tools to measure and interact with mechanical components in real-time.</p>
</div>

<div id="video4" class="video-section">
  <iframe src="https://www.youtube.com/embed/a1gV8AOMNJc" frameborder="0" allowfullscreen></iframe>
  <p><b>Smart NPC in VR:</b> Speech-to-Text, LLaMA AI, and Text-to-Speech to create smart VR characters.</p>
</div>

<div id="video5" class="video-section">
  <iframe src="https://www.youtube.com/embed/SuJQdxP6HJc" frameborder="0" allowfullscreen></iframe>
  <p><b>VR Table Tennis:</b> Realistic VR ping pong simulation with physics-based mechanics.</p>
</div>

<div id="video6" class="video-section">
  <iframe src="https://www.youtube.com/embed/2eogtswgexA" frameborder="0" allowfullscreen></iframe>
  <p><b>Gorilla vs 100 Men:</b> VR action game with immersive combat using VR controllers.</p>
</div>

<script>
function showVideo(id) {
  // Hide all video sections and stop playback
  document.querySelectorAll('.video-section').forEach(v => {
    v.style.display = "none";
    let iframe = v.querySelector("iframe");
    iframe.src = iframe.src; // reset to stop audio
  });

  // Show selected video
  document.getElementById(id).style.display = "block";

  // Smooth scroll to the video
  document.getElementById(id).scrollIntoView({ behavior: "smooth" });
}
</script>
