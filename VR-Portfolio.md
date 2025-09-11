---
layout: page
title: "VR Portfolio"
permalink: /vr-portfolio/
---

<style>
  body {
    font-family: "Poppins", sans-serif;
    background: linear-gradient(180deg, #1a1a2e, #0f0f1f);
    color: #fff;
    margin: 0;
    padding: 0;
  }
  header {
    text-align: center;
    padding: 80px 20px;
  }
  header h1 {
    font-size: 3em;
    margin: 0;
  }
  header p {
    font-size: 1.2em;
    color: #aaa;
  }
  .portfolio {
    padding: 50px;
    text-align: center;
  }
  .portfolio h2 {
    font-size: 2em;
    margin-bottom: 20px;
  }
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
  }
  .card {
    background: #111;
    border-radius: 12px;
    overflow: hidden;
    cursor: pointer;
    box-shadow: 0 4px 10px rgba(0,0,0,0.4);
    transition: transform 0.3s ease;
  }
  .card:hover {
    transform: scale(1.05);
  }
  .card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
  }
  .card-title {
    padding: 10px;
    font-weight: bold;
    text-align: center;
  }

  /* Modal */
  .modal {
    display: none;
    position: fixed;
    z-index: 999;
    left: 0; top: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.8);
    justify-content: center;
    align-items: center;
  }
  .modal-content {
    background: #fff;
    color: #000;
    padding: 20px;
    max-width: 800px;
    width: 90%;
    border-radius: 12px;
    position: relative;
  }
  .modal-content iframe {
    width: 100%;
    height: 400px;
    margin-bottom: 20px;
  }
  .close {
    position: absolute;
    top: 10px; right: 20px;
    font-size: 28px;
    font-weight: bold;
    color: #000;
    cursor: pointer;
  }
</style>

<header>
  <h1>Hi, I am Javed</h1>
  <p>XR Developer – VR/AR Prototyper – AI-driven Robotics</p>
</header>

<section class="portfolio">
  <h2>Portfolio</h2>
  <div class="grid">
    <!-- Project 1 -->
    <div class="card" onclick="openModal('modal1')">
      <img src="/assets/images/gearbox.png" alt="Gearbox VR">
      <div class="card-title">Interactive Gear Box Assembly</div>
    </div>

    <!-- Project 2 -->
    <div class="card" onclick="openModal('modal2')">
      <img src="/assets/images/inspection.png" alt="Inspection VR">
      <div class="card-title">Inspection of Mechanical Components</div>
    </div>

    <!-- Project 3 -->
    <div class="card" onclick="openModal('modal3')">
      <img src="/assets/images/measurement.png" alt="Measurement VR">
      <div class="card-title">Real-time Measurement</div>
    </div>

    <!-- Project 4 -->
    <div class="card" onclick="openModal('modal4')">
      <img src="/assets/images/npc.png" alt="NPC VR">
      <div class="card-title">Smart NPC in VR</div>
    </div>

    <!-- Project 5 -->
    <div class="card" onclick="openModal('modal5')">
      <img src="/assets/images/tabletennis.png" alt="Table Tennis VR">
      <div class="card-title">VR Table Tennis</div>
    </div>

    <!-- Project 6 -->
    <div class="card" onclick="openModal('modal6')">
      <img src="/assets/images/gorilla.png" alt="Gorilla VR">
      <div class="card-title">Gorilla vs 100 Men</div>
    </div>
  </div>
</section>

<!-- Modal Templates -->

<div id="modal1" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal('modal1')">&times;</span>
    <h2>Interactive Gear Box Assembly</h2>
    <iframe src="https://www.youtube.com/embed/UaA2s17bcwA" frameborder="0" allowfullscreen></iframe>
    <p><b>About:</b> Step-by-step VR guide for assembling a gearbox, improving efficiency and reducing errors.</p>
    <p><b>Tech Stack:</b> Unity3D, C#, XR Toolkit, Oculus SDK</p>
  </div>
</div>

<div id="modal2" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal('modal2')">&times;</span>
    <h2>Inspection of Mechanical Components</h2>
    <iframe src="https://www.youtube.com/embed/sI5wcQxgHYk" frameborder="0" allowfullscreen></iframe>
    <p><b>About:</b> VR system highlights missing mechanical parts in real time for clear visualization.</p>
    <p><b>Tech Stack:</b> Unity3D, C#, OpenXR, Shader Graph</p>
  </div>
</div>

<div id="modal3" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal('modal3')">&times;</span>
    <h2>Real-time Measurement</h2>
    <iframe src="https://www.youtube.com/embed/ggCbe4o8uC0" frameborder="0" allowfullscreen></iframe>
    <p><b>About:</b> Immersive VR environment where users measure distances/dimensions in real-time.</p>
    <p><b>Tech Stack:</b> Unity3D, C#, XR Toolkit, Physics Engine</p>
  </div>
</div>

<div id="modal4" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal('modal4')">&times;</span>
    <h2>Smart NPC in VR</h2>
    <iframe src="https://www.youtube.com/embed/a1gV8AOMNJc" frameborder="0" allowfullscreen></iframe>
    <p><b>About:</b> AI-powered NPC with speech recognition (HuggingFace STT, Groq LLaMA, Speechify TTS).</p>
    <p><b>Tech Stack:</b> Unity3D, C#, HuggingFace STT, Groq LLaMA, Speechify TTS</p>
  </div>
</div>

<div id="modal5" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal('modal5')">&times;</span>
    <h2>VR Table Tennis</h2>
    <iframe src="https://www.youtube.com/embed/SuJQdxP6HJc" frameborder="0" allowfullscreen></iframe>
    <p><b>About:</b> Physics-accurate VR table tennis with realistic responsiveness.</p>
    <p><b>Tech Stack:</b> Unity3D, C#, XR Toolkit, Physics-based AI</p>
  </div>
</div>

<div id="modal6" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal('modal6')">&times;</span>
    <h2>Gorilla vs 100 Men</h2>
    <iframe src="https://www.youtube.com/embed/2eogtswgexA" frameborder="0" allowfullscreen></iframe>
    <p><b>About:</b> Action VR game with physics-based combat where a gorilla faces waves of enemies.</p>
    <p><b>Tech Stack:</b> Unity3D, C#, XR Toolkit, Physics-based AI</p>
  </div>
</div>

<script>
  function openModal(id) {
    document.getElementById(id).style.display = "flex";
  }
  function closeModal(id) {
    document.getElementById(id).style.display = "none";
  }
</script>
