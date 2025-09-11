<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>VR Portfolio - Javed</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom, #0f2027, #203a43, #2c5364);
      color: #fff;
      text-align: center;
    }

    /* Navbar */
    nav {
      background: rgba(0,0,0,0.8);
      padding: 15px;
      display: flex;
      justify-content: center;
      gap: 40px;
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    nav a {
      text-decoration: none;
      color: #fff;
      font-weight: bold;
      font-size: 1.1em;
    }
    nav a:hover {
      color: #00ffcc;
    }

    h1, h2 {
      margin-top: 30px;
    }

    /* Portfolio grid */
    .portfolio-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 30px;
      padding: 40px;
      max-width: 1400px;
      margin: auto;
    }
    .card {
      background: rgba(255,255,255,0.05);
      border-radius: 12px;
      padding: 15px;
      cursor: pointer;
      transition: transform 0.3s ease;
    }
    .card:hover {
      transform: scale(1.05);
      background: rgba(255,255,255,0.1);
    }
    .card iframe {
      width: 100%;
      height: 250px;
      border-radius: 10px;
    }
    .card h3 {
      margin: 15px 0 10px;
    }

    /* Modal */
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.9);
      justify-content: center;
      align-items: center;
      z-index: 2000;
      padding: 30px;
      overflow-y: auto;
    }
    .modal-content {
      background: #111;
      color: #fff;
      max-width: 900px;
      width: 100%;
      padding: 30px;
      border-radius: 12px;
      text-align: left;
    }
    .modal iframe {
      width: 100%;
      height: 400px;
      border-radius: 10px;
    }
    .modal h2 {
      margin-top: 20px;
    }
    .modal p {
      margin: 10px 0;
      line-height: 1.5;
    }
    .close-btn {
      float: right;
      font-size: 22px;
      cursor: pointer;
      color: #ff5555;
    }
  </style>
</head>
<body>

  <!-- Navbar -->
  <nav>
    <a href="#portfolio">Portfolio</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </nav>

  <!-- Hero -->
  <h1>Hi, I am Javed</h1>
  <p>XR Developer – VR/AR Prototyper – AI-driven Robotics</p>

  <!-- Portfolio Grid -->
  <h2 id="portfolio">Portfolio</h2>
  <div class="portfolio-grid">

    <!-- Project 1 -->
    <div class="card" onclick="openModal('modal1')">
      <iframe src="https://www.youtube.com/embed/UaA2s17bcwA" allowfullscreen></iframe>
      <h3>Interactive Gear Box Assembly</h3>
    </div>

    <!-- Project 2 -->
    <div class="card" onclick="openModal('modal2')">
      <iframe src="https://www.youtube.com/embed/sI5wcQxgHYk" allowfullscreen></iframe>
      <h3>Inspection of Mechanical Components in VR</h3>
    </div>

    <!-- Project 3 -->
    <div class="card" onclick="openModal('modal3')">
      <iframe src="https://www.youtube.com/embed/ggCbe4o8uC0" allowfullscreen></iframe>
      <h3>Real-time Measurement of Mechanical Components</h3>
    </div>

    <!-- Project 4 -->
    <div class="card" onclick="openModal('modal4')">
      <iframe src="https://www.youtube.com/embed/a1gV8AOMNJc" allowfullscreen></iframe>
      <h3>Smart NPC in VR</h3>
    </div>

    <!-- Project 5 -->
    <div class="card" onclick="openModal('modal5')">
      <iframe src="https://www.youtube.com/embed/SuJQdxP6HJc" allowfullscreen></iframe>
      <h3>VR Table Tennis</h3>
    </div>

    <!-- Project 6 -->
    <div class="card" onclick="openModal('modal6')">
      <iframe src="https://www.youtube.com/embed/2eogtswgexA" allowfullscreen></iframe>
      <h3>Gorilla vs 100 Men</h3>
    </div>

  </div>

  <!-- Modals -->
  <div id="modal1" class="modal">
    <div class="modal-content">
      <span class="close-btn" onclick="closeModal('modal1')">&times;</span>
      <iframe src="https://www.youtube.com/embed/UaA2s17bcwA" allowfullscreen></iframe>
      <h2>Interactive Gear Box Assembly</h2>
      <p><b>Description:</b> Step-by-step interactive VR guide for gearbox assembly to improve efficiency and reduce errors.</p>
      <p><b>Tech Stack:</b> Unity3D, C#, XR Interaction Toolkit, Oculus SDK</p>
    </div>
  </div>

  <div id="modal2" class="modal">
    <div class="modal-content">
      <span class="close-btn" onclick="closeModal('modal2')">&times;</span>
      <iframe src="https://www.youtube.com/embed/sI5wcQxgHYk" allowfullscreen></iframe>
      <h2>Inspection of Mechanical Components in VR</h2>
      <p><b>Description:</b> Detects missing components in real-time with visual highlights for clear visualization.</p>
      <p><b>Tech Stack:</b> Unity3D, C#, OpenXR, Shader Graph</p>
    </div>
  </div>

  <div id="modal3" class="modal">
    <div class="modal-content">
      <span class="close-btn" onclick="closeModal('modal3')">&times;</span>
      <iframe src="https://www.youtube.com/embed/ggCbe4o8uC0" allowfullscreen></iframe>
      <h2>Real-time Measurement of Mechanical Components</h2>
      <p><b>Description:</b> Immersive VR environment that lets users measure dimensions dynamically in real-time.</p>
      <p><b>Tech Stack:</b> Unity3D, C#, XR Interaction Toolkit, Physics Engine</p>
    </div>
  </div>

  <div id="modal4" class="modal">
    <div class="modal-content">
      <span class="close-btn" onclick="closeModal('modal4')">&times;</span>
      <iframe src="https://www.youtube.com/embed/a1gV8AOMNJc" allowfullscreen></iframe>
      <h2>Smart NPC in VR</h2>
      <p><b>Description:</b> Real-time conversational VR agent using HuggingFace STT, Groq LLaMA, and Speechify TTS.</p>
      <p><b>Tech Stack:</b> Unity3D, C#, HuggingFace STT, Groq LLaMA, Speechify TTS</p>
    </div>
  </div>

  <div id="modal5" class="modal">
    <div class="modal-content">
      <span class="close-btn" onclick="closeModal('modal5')">&times;</span>
      <iframe src="https://www.youtube.com/embed/SuJQdxP6HJc" allowfullscreen></iframe>
      <h2>VR Table Tennis</h2>
      <p><b>Description:</b> Physics-accurate VR table tennis with natural responsiveness and immersive controls.</p>
      <p><b>Tech Stack:</b> Unity3D, C#, XR Interaction Toolkit, Physics-based AI</p>
    </div>
  </div>

  <div id="modal6" class="modal">
    <div class="modal-content">
      <span class="close-btn" onclick="closeModal('modal6')">&times;</span>
      <iframe src="https://www.youtube.com/embed/2eogtswgexA" allowfullscreen></iframe>
      <h2>Gorilla vs 100 Men</h2>
      <p><b>Description:</b> VR action game where players control a gorilla battling waves of enemies with physics-based hand interactions.</p>
      <p><b>Tech Stack:</b> Unity3D, C#, XR Interaction Toolkit, Physics-based AI</p>
    </div>
  </div>

  <!-- About -->
  <h2 id="about">About</h2>
  <p>Experienced XR Developer specializing in Unity, C#, and AI-driven robotics. Passionate about immersive VR/AR apps and mentoring XR devs.</p>
  <button style="padding:10px 20px; border:none; background:#00ffcc; border-radius:6px; margin:20px; cursor:pointer;">⬇ Download Resume</button>

  <!-- Contact -->
  <h2 id="contact">Contact</h2>
  <p>📍 Based in: Chennai, India</p>
  <p>
    <a href="https://github.com/" target="_blank" style="color:#00ffcc;">GitHub</a> |
    <a href="https://linkedin.com" target="_blank" style="color:#00ffcc;">LinkedIn</a> |
    <a href="mailto:youremail@example.com" style="color:#00ffcc;">Email</a>
  </p>

  <script>
    function openModal(id) {
      document.getElementById(id).style.display = "flex";
    }
    function closeModal(id) {
      let modal = document.getElementById(id);
      let iframe = modal.querySelector("iframe");
      modal.style.display = "none";
      iframe.src = iframe.src; // stop video audio
    }
  </script>

</body>
</html>
