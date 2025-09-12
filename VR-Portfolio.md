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
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 30px;
    padding: 40px;
    max-width: 1200px;
    margin: auto;
  }
  .project-card {
    background: #1e1e2f;
    border-radius: 12px;
    padding: 15px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
  }
  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0,0,0,0.5);
  }
  .project-card h3 {
    margin: 10px 0;
    color: #00ffcc;
  }
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
  .modal h3 {
    color: #00ffcc;
    margin-top: 0;
  }
  .modal-section {
    margin-bottom: 15px;
  }
  .modal-section b {
    color: #1db954;
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
    <h3>Interactive Gear Box Assembly</h3>
    <p>Step-by-step immersive VR guide for gearbox assembly.</p>
  </div>
  <div class="project-card" onclick="openModal('inspection')">
    <h3>Real Time Inspection of Mechanical Components in VR </h3>
    <p>Compare master and target models in real-time.</p>
  </div>
  <div class="project-card" onclick="openModal('measurement')">
    <h3>Real-time Measurement</h3>
    <p>Interact with components and measure dynamically.</p>
  </div>
  <div class="project-card" onclick="openModal('npc')">
    <h3>Smart NPC in VR</h3>
    <p>Voice-driven dialogue with intelligent virtual characters.</p>
  </div>
  <div class="project-card" onclick="openModal('tabletennis')">
    <h3>VR Table Tennis</h3>
    <p>Physics-accurate immersive VR table tennis experience.</p>
  </div>
  <div class="project-card" onclick="openModal('gorilla')">
    <h3>Gorilla vs 100 Men</h3>
    <p>Action-packed VR game with physics-based combat.</p>
  </div>
</div>

<!-- Modals -->
<div id="gearbox" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('gearbox')">&times;</span>
    
    <!-- Video -->
    <iframe src="https://www.youtube.com/embed/UaA2s17bcwA" allowfullscreen></iframe>

    <!-- Title -->
    <h3 class="modal-title">Interactive Gear Box Assembly in VR</h3>

    <!-- Content Section -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>VR-based mechanical gearbox assembly simulation enabling hands-on learning, improved task efficiency, and reduced assembly errors.</p>
      </div>
      
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole developer.</p>
      </div>
      
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Step-by-step guided assembly</li>
          <li>Interactive VR component handling</li>
          <li>Intuitive VR UI for navigation & instructions</li>
        </ul>
        <p>Implemented within 3 days</p>
      </div>
      
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, Meta All-in-One SDK, and Meta XR Interaction Toolkit</p>
      </div>
    </div>
  </div>
</div>

<!-- Add CSS -->
<style>
  .modal-content {
    text-align: center; /* Centers everything */
    padding: 20px;
  }

  .modal-title {
    margin-top: 15px;
    font-size: 22px;
    font-weight: bold;
  }

  .modal-details {
    margin-top: 20px;
  }

  .modal-section {
    margin: 15px 0;
  }

  .modal-section h4 {
    margin-bottom: 8px;
    font-size: 18px;
    font-weight: bold;
    color: #00ffcc; /* Highlighted heading */
  }

  .modal-section p {
    margin: 5px 0 0;
    font-size: 16px;
    line-height: 1.5;
  }

  .modal-section ul {
    list-style-type: disc;
    text-align: left; /* Keep bullets aligned */
    display: inline-block; /* Center as a block */
    margin: 0 auto 10px;
    padding-left: 20px;
    font-size: 16px;
    line-height: 1.5;
  }
</style>



<!-- Inspection of Mechanical Components -->
<div id="inspection" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('inspection')">&times;</span>
    
    <!-- Video -->
    <iframe src="https://www.youtube.com/embed/YOUR_VIDEO_ID" allowfullscreen></iframe>

    <!-- Title -->
    <h3 class="modal-title">Inspection of Mechanical Components</h3>

    <!-- Content Section -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Interactive VR target–model comparison tool with real-time missing part detection, UI highlights, and dynamic color visualization.</p>
      </div>
      
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole developer.</p>
      </div>
      
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Reference & Target Model Alignment</li>
          <li>Mesh Collider position and size</li>
          <li>Real Time Color feedback</li>
          <li>UI Integration</li>
        </ul>
        <p>Implemented within 3 days</p>
      </div>
      
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, Meta All-in-One SDK, and Meta XR Interaction Toolkit</p>
      </div>

      <div class="modal-section">
        <h4>Future Goals</h4>
        <p>Extension to AR</p>
      </div>
    </div>
  </div>
</div>

<!-- Add CSS -->
<style>
  .modal-content {
    text-align: center; /* Centers everything */
    padding: 20px;
  }

  .modal-title {
    margin-top: 15px;
    font-size: 22px;
    font-weight: bold;
  }

  .modal-details {
    margin-top: 20px;
  }

  .modal-section {
    margin: 15px 0;
  }

  .modal-section h4 {
    margin-bottom: 8px;
    font-size: 18px;
    font-weight: bold;
    color: #00ffcc; /* Highlighted heading */
  }

  .modal-section p {
    margin: 5px 0 0;
    font-size: 16px;
    line-height: 1.5;
  }

  .modal-section ul {
    list-style-type: disc;
    text-align: left; /* Bullets aligned left */
    display: inline-block; /* Keeps bullets centered as a block */
    margin: 0 auto 10px;
    padding-left: 20px;
    font-size: 16px;
    line-height: 1.5;
  }
</style>




<div id="measurement" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('measurement')">&times;</span>
    <iframe src="https://www.youtube.com/embed/ggCbe4o8uC0" allowfullscreen></iframe>
    <h3>Real-time Measurement</h3>
  </div>
</div>

<div id="npc" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('npc')">&times;</span>
    <iframe src="https://www.youtube.com/embed/a1gV8AOMNJc" allowfullscreen></iframe>
    <h3>Smart NPC in VR</h3>
  </div>
</div>

<div id="tabletennis" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('tabletennis')">&times;</span>
    <iframe src="https://www.youtube.com/embed/SuJQdxP6HJc" allowfullscreen></iframe>
    <h3>VR Table Tennis</h3>
  </div>
</div>

<div id="gorilla" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('gorilla')">&times;</span>
    <iframe src="https://www.youtube.com/embed/2eogtswgexA" allowfullscreen></iframe>
    <h3>Gorilla vs 100 Men</h3>
  </div>
</div>

<!-- About Section -->
<h2 id="about">About</h2>
<p>Master’s in Engineering Design, IITM | Crafting VR Experiences with AI</p>

<!-- Contact Section -->
<h2 id="contact">Contact</h2>
<p>Feel free to reach out, I’d love to connect with you!</p>
<p><b>Based in:</b> Chennai, India</p>

<footer>
  <a href="https://github.com/Javed-Akhter-Shaik" target="_blank">🐙 GitHub</a>
  <a href="https://www.linkedin.com/in/javed-akhter-shaik-76836320b/" target="_blank">🔗 LinkedIn</a>
  <a href="mailto:shaikjaved672@gmail.com">📧 Email</a>
</footer>

<script>
  function openModal(id) {
    const modal = document.getElementById(id);
    modal.style.display = "flex";

    // Add listener to close when clicking outside modal-content
    modal.addEventListener("click", function(e) {
      if (e.target === modal) {
        closeModal(id);
      }
    });
  }

  function closeModal(id) {
    const modal = document.getElementById(id);
    modal.style.display = "none";
    let iframe = modal.querySelector("iframe");
    if (iframe) iframe.src = iframe.src; // stop video
  }
</script>
