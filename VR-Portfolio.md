---
layout: page
title: "VR Portfolio"
permalink: /vr-portfolio/
---

<style>
  body {
    font-family: 'Arial', sans-serif;
    background: linear-gradient(to bottom, #101820, #1b2735);
    color: #f2f2f2;
    margin: 0;
    padding: 0;
    text-align: center;
  }
  nav {
    background: transparent;
    padding: 20px;
  }
  nav a {
    margin: 0 20px;
    color: #ddd;
    text-decoration: none;
    font-weight: bold;
    font-size: 18px;
  }
  nav a:hover {
    color: #fff;
  }
  h1, h2 {
    margin-top: 20px;
  }

  /* Portfolio grid */
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 25px;
    padding: 40px;
    max-width: 1200px;
    margin: auto;
  }

  /* Project card with thumbnail */
  .project-card {
    position: relative;
    border-radius: 12px;
    overflow: hidden;
    cursor: pointer;
    box-shadow: 0 4px 10px rgba(0,0,0,0.5);
    transition: transform 0.3s ease;
  }
  .project-card:hover {
    transform: translateY(-5px);
  }
  .project-card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    display: block;
  }

  /* Overlay text */
  .project-info {
    position: absolute;
    bottom: 0;
    left: 0; right: 0;
    background: rgba(0,0,0,0.65);
    color: #fff;
    padding: 10px;
    font-size: 14px;
    text-align: center;
  }
  .project-info h3 {
    margin: 0;
    font-size: 16px;
    color: #00ffcc;
  }
  .project-info p {
    margin: 5px 0 0;
    font-size: 12px;
    color: #ddd;
  }

  /* Modal */
  .modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0; top: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.85);
    justify-content: center;
    align-items: center;
    overflow-y: auto;
  }
  .modal-content {
    background: #222;
    padding: 20px;
    border-radius: 12px;
    max-width: 900px;
    width: 90%;
    position: relative;
    text-align: left;
    color: #eee;
  }
  .modal iframe, .modal img {
    width: 100%;
    height: 400px;
    border-radius: 8px;
    margin-bottom: 20px;
  }
  .close-btn {
    position: absolute;
    top: 10px; right: 15px;
    color: #fff;
    font-size: 28px;
    cursor: pointer;
  }

  footer {
    background: #12121b;
    padding: 30px;
    margin-top: 50px;
  }
  footer a {
    margin: 0 10px;
    color: #bbb;
    font-size: 20px;
  }
  footer a:hover {
    color: #fff;
  }
</style>

<!-- Navigation -->
<nav>
  <a href="#portfolio">Portfolio</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>

<!-- Intro -->
<h1>Hi, I am Javed</h1>
<p class="tagline">XR Developer – VR Prototyper </p>

<!-- Portfolio Section -->
<h2 id="portfolio">Portfolio</h2>
<div class="portfolio-grid">

  <div class="project-card" onclick="openModal('gearbox')">
    <img src="/assets/thumbnails/gearbox.jpg" alt="Gearbox Project">
    <div class="project-info">
      <h3>Interactive Gear Box Assembly</h3>
      <p>Immersive VR guide for assembly</p>
    </div>
  </div>

  <div class="project-card" onclick="openModal('inspection')">
    <img src="/assets/thumbnails/inspection.jpg" alt="Inspection Project">
    <div class="project-info">
      <h3>Inspection of Components</h3>
      <p>Master vs target model detection</p>
    </div>
  </div>

  <div class="project-card" onclick="openModal('measurement')">
    <img src="/assets/thumbnails/measurement.jpg" alt="Measurement Project">
    <div class="project-info">
      <h3>Real-time Measurement</h3>
      <p>Dynamic VR measurement tools</p>
    </div>
  </div>

  <div class="project-card" onclick="openModal('npc')">
    <img src="/assets/thumbnails/npc.jpg" alt="NPC Project">
    <div class="project-info">
      <h3>Smart NPC in VR</h3>
      <p>Voice-driven intelligent NPC</p>
    </div>
  </div>

  <div class="project-card" onclick="openModal('tabletennis')">
    <img src="/assets/thumbnails/tabletennis.jpg" alt="Table Tennis Project">
    <div class="project-info">
      <h3>VR Table Tennis</h3>
      <p>Physics-accurate VR gameplay</p>
    </div>
  </div>

  <div class="project-card" onclick="openModal('gorilla')">
    <img src="/assets/thumbnails/gorilla.jpg" alt="Gorilla Project">
    <div class="project-info">
      <h3>Gorilla vs 100 Men</h3>
      <p>Action-packed VR combat</p>
    </div>
  </div>

</div>

<!-- Example Modal -->
<div id="gearbox" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('gearbox')">&times;</span>
    <iframe src="https://www.youtube.com/embed/UaA2s17bcwA" allowfullscreen></iframe>
    <h3>Interactive Gear Box Assembly</h3>
    <p><b>About:</b> Interactive VR guide for gearbox assembly to enhance learning, reduce errors, and improve efficiency.</p>
  </div>
</div>

<!-- Repeat your other modals here -->

<footer>
  <a href="https://github.com/Javed-Akhter-Shaik" target="_blank">🐙 GitHub</a>
  <a href="https://www.linkedin.com/in/javed-akhter-shaik-76836320b/" target="_blank">🔗 LinkedIn</a>
  <a href="mailto:shaikjaved672@gmail.com">📧 Email</a>
</footer>

<script>
  function openModal(id) {
    const modal = document.getElementById(id);
    modal.style.display = "flex";

    // Close if clicking outside content
    modal.addEventListener("click", function(e) {
      if (e.target === modal) closeModal(id);
    });
  }

  function closeModal(id) {
    const modal = document.getElementById(id);
    modal.style.display = "none";
    let iframe = modal.querySelector("iframe");
    if (iframe) iframe.src = iframe.src; // reset video
  }
</script>
