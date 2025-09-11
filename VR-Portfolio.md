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
    grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
    gap: 35px;
    padding: 40px;
    max-width: 1300px;
    margin: auto;
  }
  .project-card {
    background: #1e1e2f;
    border-radius: 12px;
    padding: 20px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
    text-align: left;
  }
  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0,0,0,0.5);
  }
  .project-card h3 {
    margin: 10px 0;
    color: #00ffcc;
  }
  .project-card p {
    font-size: 14px;
    line-height: 1.6em;
    margin: 8px 0;
  }
  .tech-stack {
    font-style: italic;
    color: #bbb;
    font-size: 13px;
    margin-top: 8px;
  }
  .skills {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin: 20px 0;
  }
  .skill-tag {
    background: #2c2c44;
    padding: 8px 15px;
    border-radius: 20px;
    font-size: 14px;
    color: #fff;
  }
  .resume-btn {
    display: inline-block;
    padding: 12px 25px;
    margin: 20px 0;
    background: #1db954;
    color: white;
    text-decoration: none;
    border-radius: 8px;
    font-weight: bold;
  }
  .resume-btn:hover {
    background: #1aa34a;
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
  /* Modal styling */
  .modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0; top: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.8);
    justify-content: center;
    align-items: center;
  }
  .modal-content {
    background: #222;
    padding: 20px;
    border-radius: 12px;
    max-width: 950px;
    width: 95%;
    position: relative;
  }
  .modal iframe {
    width: 100%;
    height: 520px;
    border: none;
  }
  .close-btn {
    position: absolute;
    top: 10px; right: 15px;
    color: #fff;
    font-size: 28px;
    cursor: pointer;
  }
</style>

<!-- Navigation -->
<nav>
  <a href="#portfolio">Portfolio</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>

<h1>Hi, I am Javed</h1>
<p>XR Developer – VR/AR Prototyper – AI-driven Robotics</p>

<!-- Portfolio Section -->
<h2 id="portfolio">Portfolio</h2>
<div class="portfolio-grid">

  <div class="project-card" data-video="https://www.youtube.com/embed/UaA2s17bcwA">
    <h3>Interactive Gear Box Assembly</h3>
    <p>Create an interactive VR guide for gearbox assembly, helping users learn step-by-step, reduce errors, and improve efficiency in maintenance tasks.</p>
    <p class="tech-stack">Tech stack: Unity3D, VR Interaction, Physics-based Assembly</p>
  </div>

  <div class="project-card" data-video="https://www.youtube.com/embed/sI5wcQxgHYk">
    <h3>Inspection of Mechanical Components</h3>
    <p>Developed VR environment for real-time comparison of master vs target models. Missing parts are auto-detected and highlighted instantly.</p>
    <p class="tech-stack">Tech stack: Unity3D, Real-time Detection, VR UI</p>
  </div>

  <div class="project-card" data-video="https://www.youtube.com/embed/ggCbe4o8uC0">
    <h3>Real-time Measurement</h3>
    <p>Immersive VR project to interact with mechanical components and measure distances & dimensions dynamically.</p>
    <p class="tech-stack">Tech stack: Unity3D, VR Interaction, Measurement Tools</p>
  </div>

  <div class="project-card" data-video="https://www.youtube.com/embed/a1gV8AOMNJc">
    <h3>Smart NPC in VR</h3>
    <p>Interactive conversational NPCs with voice-driven dialogue. Integrated STT, LLM-based processing, and expressive TTS in Unity.</p>
    <p class="tech-stack">Tech stack: Unity3D, HuggingFace, Groq Llama, Speechify</p>
  </div>

  <div class="project-card" data-video="https://www.youtube.com/embed/SuJQdxP6HJc">
    <h3>VR Table Tennis</h3>
    <p>Physics-accurate immersive VR table tennis. Simulates real-world ping pong with intuitive motion controls and spatial audio.</p>
    <p class="tech-stack">Tech stack: Unity3D, VR Physics, Spatial Audio</p>
  </div>

  <div class="project-card" data-video="https://www.youtube.com/embed/2eogtswgexA">
    <h3>Gorilla vs 100 Men</h3>
    <p>Action-packed VR combat game where players control a gorilla against enemy waves. Features physics-based grabbing, throwing, and combat.</p>
    <p class="tech-stack">Tech stack: Unity3D, Physics Hand Interaction, VR Combat</p>
  </div>

</div>

<!-- Video Modal -->
<div class="modal" id="videoModal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal()">&times;</span>
    <iframe id="videoFrame" src="" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>
</div>

<!-- About Section -->
<h2 id="about">About</h2>
<div class="skills">
  <span class="skill-tag">VR/AR Development</span>
  <span class="skill-tag">Unity3D</span>
  <span class="skill-tag">C#</span>
  <span class="skill-tag">AI Robotics</span>
  <span class="skill-tag">Python</span>
  <span class="skill-tag">Machine Learning</span>
  <span class="skill-tag">OpenXR</span>
</div>
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
  const cards = document.querySelectorAll('.project-card');
  const modal = document.getElementById('videoModal');
  const videoFrame = document.getElementById('videoFrame');

  cards.forEach(card => {
    card.addEventListener('click', () => {
      const videoUrl = card.getAttribute('data-video');
      videoFrame.src = videoUrl + "?autoplay=1";
      modal.style.display = "flex";
    });
  });

  function closeModal() {
    modal.style.display = "none";
    videoFrame.src = ""; // Stops audio when modal closes
  }
</script>
