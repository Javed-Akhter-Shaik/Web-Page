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
    grid-template-columns: repeat(3, 1fr); /* Exactly 3 per row */
    gap: 25px;
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
    <div class="card" onclick="openModal('modal1','https://www.youtube.com/embed/UaA2s17bcwA')">
      <img src="/assets/images/gearbox.png" alt="Gearbox VR">
      <div class="card-title">Interactive Gear Box Assembly</div>
    </div>

    <!-- Project 2 -->
    <div class="card" onclick="openModal('modal2','https://www.youtube.com/embed/sI5wcQxgHYk')">
      <img src="/assets/images/inspection.png" alt="Inspection VR">
      <div class="card-title">Inspection of Mechanical Components</div>
    </div>

    <!-- Project 3 -->
    <div class="card" onclick="openModal('modal3','https://www.youtube.com/embed/ggCbe4o8uC0')">
      <img src="/assets/images/measurement.png" alt="Measurement VR">
      <div class="card-title">Real-time Measurement</div>
    </div>

    <!-- Project 4 -->
    <div class="card" onclick="openModal('modal4','https://www.youtube.com/embed/a1gV8AOMNJc')">
      <img src="/assets/images/npc.png" alt="NPC VR">
      <div class="card-title">Smart NPC in VR</div>
    </div>

    <!-- Project 5 -->
    <div class="card" onclick="openModal('modal5','https://www.youtube.com/embed/SuJQdxP6HJc')">
      <img src="/assets/images/tabletennis.png" alt="Table Tennis VR">
      <div class="card-title">VR Table Tennis</div>
    </div>

    <!-- Project 6 -->
    <div class="card" onclick="openModal('modal6','https://www.youtube.com/embed/2eogtswgexA')">
      <img src="/assets/images/gorilla.png" alt="Gorilla VR">
      <div class="card-title">Gorilla vs 100 Men</div>
    </div>
  </div>
</section>

<!-- Modal (shared) -->
<div id="videoModal" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal()">&times;</span>
    <h2 id="modalTitle"></h2>
    <iframe id="modalVideo" src="" frameborder="0" allowfullscreen></iframe>
    <p id="modalDesc"></p>
    <p id="modalTech"></p>
  </div>
</div>

<script>
  function openModal(id, videoUrl) {
    const modal = document.getElementById("videoModal");
    const iframe = document.getElementById("modalVideo");

    // Set video URL
    iframe.src = videoUrl + "?autoplay=1";

    // Example titles/descriptions (you can customize with a JSON object)
    const titles = {
      modal1: "Interactive Gear Box Assembly",
      modal2: "Inspection of Mechanical Components",
      modal3: "Real-time Measurement",
      modal4: "Smart NPC in VR",
      modal5: "VR Table Tennis",
      modal6: "Gorilla vs 100 Men"
    };

    const descs = {
      modal1: "Step-by-step VR guide for assembling a gearbox.",
      modal2: "VR system highlights missing mechanical parts in real time.",
      modal3: "Measure distances & dimensions dynamically in VR.",
      modal4: "AI-powered NPC with HuggingFace STT + Groq LLaMA.",
      modal5: "Physics-accurate VR table tennis simulation.",
      modal6: "VR combat game where a gorilla fights human enemies."
    };

    const tech = {
      modal1: "Unity3D, C#, XR Toolkit, Oculus SDK",
      modal2: "Unity3D, C#, OpenXR, Shader Graph",
      modal3: "Unity3D, C#, XR Toolkit, Physics Engine",
      modal4: "Unity3D, C#, HuggingFace STT, Groq LLaMA, Speechify TTS",
      modal5: "Unity3D, C#, XR Toolkit, Physics-based AI",
      modal6: "Unity3D, C#, XR Toolkit, Physics-based AI"
    };

    document.getElementById("modalTitle").innerText = titles[id];
    document.getElementById("modalDesc").innerText = descs[id];
    document.getElementById("modalTech").innerText = "Tech Stack: " + tech[id];

    modal.style.display = "flex";
  }

  function closeModal() {
    const modal = document.getElementById("videoModal");
    const iframe = document.getElementById("modalVideo");

    modal.style.display = "none";

    // Stop the video (clear src)
    iframe.src = "";
  }
</script>
