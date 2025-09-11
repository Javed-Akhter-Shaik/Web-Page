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
    <h3>Inspection of Mechanical Components</h3>
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

<div id="inspection" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('inspection')">&times;</span>
    <iframe src="https://www.youtube.com/embed/sI5wcQxgHYk" allowfullscreen></iframe>
    <h3>Inspection of Mechanical Components</h3>
    <div class="modal-section"><b>About:</b> VR environment for real-time comparison of master vs target models.</div>
    <div class="modal-section"><b>Highlights:</b> Missing components auto-detected & highlighted instantly.</div>
    <div class="modal-section"><b>Tech stack:</b> Unity3D, VR UI, Real-time Detection</div>
    <div class="modal-section"><b>Contributions:</b> Designed real-time detection & highlighting system.</div>
    <div class="modal-section"><b>Future Goals:</b> Expand to CAD model integration.</div>
  </div>
</div>

<div id="measurement" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('measurement')">&times;</span>
    <iframe src="https://www.youtube.com/embed/ggCbe4o8uC0" allowfullscreen></iframe>
    <h3>Real-time Measurement</h3>
    <div class="modal-section"><b>About:</b> Immersive VR project to measure distances and dimensions dynamically.</div>
    <div class="modal-section"><b>Tech stack:</b> Unity3D, VR Interaction, Measurement Tools</div>
    <div class="modal-section"><b>Highlights:</b> Enabled dimension measurements directly in VR.</div>
    <div class="modal-section"><b>Contributions:</b> Built distance calculation tool in VR.</div>
    <div class="modal-section"><b>Future Goals:</b> Add precision calibration & CAD model export.</div>
  </div>
</div>

<div id="npc" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('npc')">&times;</span>
    <iframe src="https://www.youtube.com/embed/a1gV8AOMNJc" allowfullscreen></iframe>
    <h3>Smart NPC in VR</h3>
    <div class="modal-section"><b>About:</b> Conversational NPCs with voice-driven dialogue.</div>
    <div class="modal-section"><b>Highlights:</b> STT → LLM → TTS pipeline for natural conversations.</div>
    <div class="modal-section"><b>Tech stack:</b> Unity3D, HuggingFace, Groq Llama, Speechify</div>
    <div class="modal-section"><b>Contributions:</b> Integrated STT, NLU, TTS inside Unity.</div>
    <div class="modal-section"><b>Future Goals:</b> Expand NPC behavior library.</div>
  </div>
</div>

<div id="tabletennis" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('tabletennis')">&times;</span>
    <iframe src="https://www.youtube.com/embed/SuJQdxP6HJc" allowfullscreen></iframe>
    <h3>VR Table Tennis</h3>
    <div class="modal-section"><b>About:</b> Physics-accurate immersive VR table tennis simulating real-world responsiveness.</div>
    <div class="modal-section"><b>Tech stack:</b> Unity3D, VR Physics, Spatial Audio</div>
    <div class="modal-section"><b>Highlights:</b> Realistic motion & spatial sound.</div>
    <div class="modal-section"><b>Contributions:</b> Physics engine for ball & paddle.</div>
    <div class="modal-section"><b>Future Goals:</b> Add multiplayer support.</div>
  </div>
</div>

<div id="gorilla" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('gorilla')">&times;</span>
    <iframe src="https://www.youtube.com/embed/2eogtswgexA" allowfullscreen></iframe>
    <h3>Gorilla vs 100 Men</h3>
    <div class="modal-section"><b>About:</b> Action-packed VR combat game where players control a gorilla.</div>
    <div class="modal-section"><b>Tech stack:</b> Unity3D, Physics Hand Interaction, VR Combat</div>
    <div class="modal-section"><b>Highlights:</b> Dynamic forest combat environment.</div>
    <div class="modal-section"><b>Contributions:</b> Built combat physics & control system.</div>
    <div class="modal-section"><b>Future Goals:</b> Expand AI behavior & multiplayer mode.</div>
  </div>
</div>

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
