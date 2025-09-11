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

  /* Navbar */
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

  /* Intro */
  h1 {
    font-size: 3em;
    margin-top: 40px;
    text-transform: uppercase;
  }
  h2 {
    margin-top: 20px;
    font-size: 2em;
  }
  p.tagline {
    font-size: 1.2em;
    color: #aaa;
  }

  /* Portfolio grid */
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 30px;
    padding: 40px;
    max-width: 1200px;
    margin: auto;
  }
  .project-card {
    position: relative;
    overflow: hidden;
    border-radius: 12px;
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0,0,0,0.5);
  }
  .project-card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    display: block;
  }
  .project-title {
    position: absolute;
    bottom: 0;
    width: 100%;
    padding: 10px;
    background: rgba(0,0,0,0.6);
    color: #fff;
    font-weight: bold;
    font-size: 1em;
    text-align: center;
  }

  /* Modal */
  .modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0; top: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.9);
    justify-content: center;
    align-items: flex-start;
    overflow-y: auto;
    padding: 40px 0;
  }
  .modal-content {
    background: #222;
    padding: 20px;
    border-radius: 12px;
    max-width: 900px;
    width: 90%;
    margin: auto;
    text-align: left;
    color: #eee;
  }
  .modal iframe {
    width: 100%;
    height: 420px;
    border-radius: 8px;
    margin-bottom: 20px;
  }
  .close-btn {
    position: absolute;
    top: 20px; right: 35px;
    color: #fff;
    font-size: 32px;
    cursor: pointer;
  }
  .modal h3 {
    color: #00ffcc;
    margin-top: 0;
  }
  .modal-section {
    margin-bottom: 12px;
    font-size: 0.95em;
    line-height: 1.5em;
  }
  .modal-section b {
    color: #1db954;
  }

  /* Footer */
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
<p class="tagline">XR Developer – VR/AR Prototyper – AI-driven Robotics</p>

<!-- Portfolio Section -->
<h2 id="portfolio">Portfolio</h2>
<div class="portfolio-grid">

  <div class="project-card" onclick="openModal('gearbox')">
    <img src="/assets/img/gearbox.jpg" alt="Gearbox">
    <div class="project-title">Interactive Gear Box Assembly</div>
  </div>

  <div class="project-card" onclick="openModal('inspection')">
    <img src="/assets/img/inspection.jpg" alt="Inspection">
    <div class="project-title">Inspection of Mechanical Components</div>
  </div>

  <div class="project-card" onclick="openModal('measurement')">
    <img src="/assets/img/measurement.jpg" alt="Measurement">
    <div class="project-title">Real-time Measurement</div>
  </div>

  <div class="project-card" onclick="openModal('npc')">
    <img src="/assets/img/npc.jpg" alt="NPC">
    <div class="project-title">Smart NPC in VR</div>
  </div>

  <div class="project-card" onclick="openModal('tabletennis')">
    <img src="/assets/img/tabletennis.jpg" alt="Table Tennis">
    <div class="project-title">VR Table Tennis</div>
  </div>

  <div class="project-card" onclick="openModal('gorilla')">
    <img src="/assets/img/gorilla.jpg" alt="Gorilla vs 100 Men">
    <div class="project-title">Gorilla vs 100 Men</div>
  </div>

</div>

<!-- Example Modal (repeat for each project) -->
<div id="gearbox" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('gearbox')">&times;</span>
    <iframe src="https://www.youtube.com/embed/UaA2s17bcwA" allowfullscreen></iframe>
    <h3>Interactive Gear Box Assembly</h3>
    <div class="modal-section"><b>About:</b> Interactive VR guide for gearbox assembly to enhance learning, reduce errors, and improve efficiency.</div>
    <div class="modal-section"><b>Role:</b> Developer & Designer</div>
    <div class="modal-section"><b>Highlights:</b> Step-by-step immersive guidance, improves assembly learning, reduces errors.</div>
    <div class="modal-section"><b>Tech stack:</b> Unity3D, VR Interaction, Physics-based Assembly</div>
    <div class="modal-section"><b>Contributions:</b> Created VR assembly workflow, tested usability, optimized interaction.</div>
    <div class="modal-section"><b>Future Goals:</b> Extend to AR-based assembly instructions.</div>
  </div>
</div>

<!-- Repeat modal structure for each project (inspection, measurement, npc, tabletennis, gorilla) -->

<!-- About Section -->
<h2 id="about">About</h2>
<p>Experienced XR Developer specializing in Unity, C#, and AI-driven robotics. Passionate about building immersive VR/AR applications and mentoring XR development. Always eager to expand knowledge and collaborate on innovative projects.</p>
<a href="/assets/Javed_CV.pdf" class="resume-btn" download>📄 Download Resume</a>

<!-- Contact Section -->
<h2 id="contact">Contact</h2>
<p>Feel free to reach out, I’d love to connect with you!</p>
<p><b>Based in:</b> Chennai, India</p>

<footer>
  <a href="https://github.com/yourgithub" target="_blank">🐙 GitHub</a>
  <a href="https://linkedin.com/in/yourlinkedin" target="_blank">🔗 LinkedIn</a>
  <a href="mailto:youremail@example.com">📧 Email</a>
</footer>

<script>
  function openModal(id) {
    document.getElementById(id).style.display = "flex";
  }
  function closeModal(id) {
    document.getElementById(id).style.display = "none";
    let iframe = document.querySelector(`#${id} iframe`);
    if (iframe) iframe.src = iframe.src; // stop video
  }
</script>
