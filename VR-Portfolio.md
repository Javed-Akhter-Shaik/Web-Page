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
    grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
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


  .project-image {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 10px;
  margin-bottom: 10px;
}


  .project-image-container {
  position: relative;
  width: 100%;
  height: 180px;
  overflow: hidden;
  border-radius: 10px;
}

.project-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.6);
  opacity: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: opacity 0.3s ease;
  border-radius: 10px;
}

.project-image-container:hover .overlay {
  opacity: 1;
}

.plus {
  font-size: 48px;
  font-weight: bold;
  color: #00ffcc;
}


  #bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1; /* keep it behind all content */
  background: linear-gradient(to bottom, #101820, #1b2735); /* fallback if WebGL fails */
}


  .about-section,
.contact-section {
  max-width: 900px;
  margin: 60px auto;
  text-align: center;
}


  footer {
  background: #12121b;
  padding: 30px;
  margin-top: 50px;
  text-align: center;
}

footer a {
  margin: 0 20px;
  display: inline-block;
}

footer img {
  width: 32px;
  height: 32px;
  filter: brightness(0.85);
  transition: 0.3s ease;
}

footer img:hover {
  filter: brightness(1.2);
}


  .resume-btn {
  display: inline-block;
  margin: 20px auto;
  padding: 12px 24px;
  border: 2px solid #00ffcc;  /* same color as heading */
  border-radius: 10px;
  background: transparent;
  color: #00ffcc;   /* button text color */
  font-size: 18px;
  font-weight: 600;
  text-decoration: none;
  text-align: center;
  transition: all 0.3s ease;
}

.resume-btn:hover {
  background: #00ffcc;   /* fill background on hover */
  color: #1e1e2f;        /* dark text on hover */
  transform: scale(1.05);
}


.skills-section {
  margin: 60px auto;
  max-width: 1000px;
  text-align: center;
}

.skills-section h2 {
  font-size: 28px;
  margin-bottom: 20px;
  color: #fff;
}

.skills-container {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
  justify-content: center;
}

.skill {
  background: #3a3a4d;
  color: #fff;
  padding: 10px 18px;
  border-radius: 20px;
  font-weight: bold;
  font-size: 15px;
  transition: all 0.3s ease;
}

.skill:hover {
  background: #00ffcc;
  color: #101820;
}



  

  
</style>


<canvas id="bg"></canvas>
<script src="https://cdn.jsdelivr.net/npm/three@0.150.1/build/three.min.js"></script>

<script>
  // === Setup ===
  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(
    75,
    window.innerWidth / window.innerHeight,
    0.1,
    1000
  );

  const renderer = new THREE.WebGLRenderer({
    canvas: document.getElementById("bg"),
    alpha: true
  });
  renderer.setSize(window.innerWidth, window.innerHeight);

  // === Particles ===
  const particlesGeometry = new THREE.BufferGeometry();
  const particlesCount = 500;
  const posArray = new Float32Array(particlesCount * 3);

  for (let i = 0; i < particlesCount * 3; i++) {
    posArray[i] = (Math.random() - 0.5) * 50;
  }

  particlesGeometry.setAttribute(
    "position",
    new THREE.BufferAttribute(posArray, 3)
  );

  const particlesMaterial = new THREE.PointsMaterial({
    size: 0.05,
    color: "#00ffcc"
  });

  const particlesMesh = new THREE.Points(
    particlesGeometry,
    particlesMaterial
  );
  scene.add(particlesMesh);

  camera.position.z = 5;

  // === Animation Loop ===
  function animate() {
    requestAnimationFrame(animate);

    particlesMesh.rotation.y += 0.0015;
    particlesMesh.rotation.x += 0.0008;

    renderer.render(scene, camera);
  }

  animate();

  // === Resize Handler ===
  window.addEventListener("resize", () => {
    camera.aspect = window.innerWidth / window.innerHeight;
    camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth, window.innerHeight);
  });
</script>




<!-- Navigation -->
<nav>
  <a href="#portfolio">Portfolio</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>



<!-- Intro -->
<h1>Hi, I am Javed</h1>
<p class="tagline">XR Developer – VR Prototyper </p>


<h2 style="text-align:center; color:#00ffcc; margin-top:50px; margin-bottom:20px;">
  Master's Project (IIT Madras, Ongoing*)
</h2>



<!-- New Featured Project -->
<div class="project-card" onclick="openModal('newproject')" 
     style="max-width:1100px; margin:40px auto; text-align:center; background:#1e1e2f; border-radius:12px; padding:20px;">

  <!-- Image -->
  <div class="project-image-container" style="height:500px;">
    <img src="/Web-Page/assets/images/viz_of_pf.png" 
         alt="Visualization of Pareto Front Thumbnail" 
         class="project-image" 
         style="height:100%; object-fit:cover; border-radius:12px;">

    <div class="overlay">
      <span class="plus">+</span>
    </div>
  </div>

  <!-- Title + Subtitle -->
  <h3 style="margin-top:15px; color:#00ffcc;">Virtual Reality for Enhanced Decision Making in Multi-Objective Optimization</h3>
  <p style="font-size:18px; color:#ddd;">Master’s Project</p>
</div>




<!-- Gorilla vs 100 Men -->
<div id="gorilla" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('gorilla')">&times;</span>
    
    <!-- Video -->
    <iframe 
      src="https://www.youtube.com/embed/2eogtswgexA" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">Gorilla vs 100 Men</h3>

    <!-- Content Section -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Gorilla vs 100 Men is a VR action game where the player controls a gorilla facing off against waves of human enemies in a dynamic forest environment. The game features physics-based hand interactions for attacking, grabbing, and throwing enemies, using VR controllers for full immersion</p>
      </div>
      <div class="modal-section">
        <h4>Role</h4>
        <p>Handled Animations, Enemy and player collision detection and health management Scripts (Group project of 5 members)</p>
      </div>
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Enemy death animation</li> <li>Final IK & Puppet Master integration</li> 
          <li>Low poly optimized environment</li> </ul> <p>Prototype built within 2 weeks</p> </div>
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, Meta All-in-One SDK, Meta XR Interaction Toolkit, Maximo, Puppet Master</p>
      </div>
    </div>
  </div>
</div>

<h2 style="text-align:center; color:#00ffcc; margin-top:70px; margin-bottom:20px;">
  XR Bootcamp MVP (Group Project)
</h2>


<!-- Gorilla Featured Project -->
<div class="project-card" onclick="openModal('gorilla')" 
     style="max-width:700px; margin:40px auto; text-align:center; background:#1e1e2f; border-radius:12px; padding:20px;">
  
  <!-- Image Container -->
  <div class="project-image-container" style="height:400px;">
    <img src="/Web-Page/assets/images/gorilla_vs_100men.jpg" 
         alt="Gorilla vs 100 Men" 
         class="project-image" 
         style="height:100%; object-fit:cover; border-radius:12px;">
    <div class="overlay">
      <span class="plus">+</span>
    </div>
  </div>

  <!-- Title + Subtitle -->
  <h3 style="margin-top:15px; color:#00ffcc;">Gorilla vs 100 Men</h3>
  <p style="font-size:18px; color:#ddd;">Action-packed VR game with physics-based combat</p>
</div>


<h2 style="text-align:center; color:#00ffcc; margin-top:90px; margin-bottom:20px;">
  XR Bootcamp Prototypes (Sole Developer)
</h2>


<div class="portfolio-grid">

  <!-- Gearbox -->
  <div class="project-card" onclick="openModal('gearbox')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/gearbox.png" alt="Gear Box Assembly VR" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>Interactive Gear Box Assembly</h3>
    <p>Step-by-step immersive VR guide for gearbox assembly.</p>
  </div>

  <!-- Inspection -->
  <div class="project-card" onclick="openModal('inspection')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/inspection.png" alt="Inspection VR" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>Real Time Inspection of Mechanical Components in VR</h3>
    <p>Compare master and target models in real-time.</p>
  </div>

  <!-- Measurement -->
  <div class="project-card" onclick="openModal('measurement')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/measurement.png" alt="Measurement VR" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>Real-time Measurement</h3>
    <p>Interact with components and measure dynamically.</p>
  </div>

  <!-- NPC -->
  <div class="project-card" onclick="openModal('npc')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/npc.png" alt="NPC VR" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>Smart NPC in VR</h3>
    <p>Voice-driven dialogue with intelligent virtual characters.</p>
  </div>

  <!-- VR Table Tennis -->
  <div class="project-card" onclick="openModal('tabletennis')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/vr_table_tennis.png" alt="VR Table Tennis" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>VR Table Tennis</h3>
    <p>Physics-accurate immersive VR table tennis experience.</p>
  </div>


  <!-- VR Gun Game -->
<div class="project-card" onclick="openModal('vrgungame')">
  <div class="project-image-container">
    <img src="/Web-Page/assets/images/vr_gun_game.png" alt="VR Gun Game" class="project-image">
    <div class="overlay">
      <span class="plus">+</span>
    </div>
  </div>
  <h3>VR Gun Game</h3>
  <p>Interactive VR shooting range with modular gun system.</p>
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
        <p>Sole Developer</p>
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

<!-- New Project Modal -->
<div id="newproject" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('newproject')">&times;</span>
    
    <!-- Video -->
    <iframe 
      src="https://www.youtube.com/embed/wFQMptUKP4U" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">Virtual Reality for Enhanced Decision Making in Multi-Objective Optimization</h3>

    <!-- Content -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Developed an interactive VR-based decision-support framework/system for Engineering Design problems, enabling real-time exploration of Pareto-optimal solutions in Multi-Objective Optimization through immersive 3D CAD visualization</p>
      </div>

      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>

      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Developed a Virtual Reality semi automated framework to enhance decision-making in Multi-Objective Optimization (MOO)</li>
          <li>Built immersive Pareto front visualizations to explore trade-offs across high-dimensional objectives</li>
          <li>Applied framework to case studies including structural design & energy efficiency building problems</li>
          <li>Linked objective and solution spaces using immersive VR to enable intuitive exploration of multi-objective trade-offs</li>
          
        </ul>
        <p></p>
      </div>

      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, MatLab, python, Fusion 360, Meta XR SDK, Meta Interactions ToolKit, Full Body IK using Meta Movements SDK </p>
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
    <iframe 
      src="https://www.youtube.com/embed/sI5wcQxgHYk" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

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
        <p>Sole Developer</p>
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




<!-- Real-time Measurement -->
<div id="measurement" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('measurement')">&times;</span>
    
    <!-- Video -->
    <iframe 
      src="https://www.youtube.com/embed/ggCbe4o8uC0" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">Real-time Measurement</h3>

    <!-- Content Section -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Immersive VR environment for interacting with mechanical components and performing real-time distance and dimension measurements.</p>
      </div>
      
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Interactive Manipulation of Components</li>
          <li>Real-Time Measurement Tool</li>
          <li>Real-time Color feedback</li>
          <li>UI for real-time display of measurements</li>
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


<!-- Smart NPC in VR -->
<div id="npc" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('npc')">&times;</span>
    
    <!-- Video -->
    <iframe 
      src="https://www.youtube.com/embed/a1gV8AOMNJc" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">Smart NPC in VR</h3>

    <!-- Content Section -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Developed a VR conversational agent with real-time voice interaction, integrating HuggingFace STT, Groq Llama LLM, and Speechify TTS within Unity for seamless immersive dialogue.</p>
      </div>
      
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Real-time conversational responsiveness</li>
          <li>Real-time voice input and recognition using HuggingFace STT</li>
          <li>Natural language understanding via Groq Llama LLM</li>
          <li>Expressive voice output through Speechify TTS</li>
          <li>Fully integrated within Unity VR environment</li>
          <li>Immersive interaction with virtual characters</li>
        </ul>
        <p>Prototype built within 3 days</p>
      </div>
      
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, Meta All-in-One SDK, and Meta XR Interaction Toolkit</p>
      </div>

      <div class="modal-section">
      </div>
    </div>
  </div>
</div>


<!-- VR Table Tennis -->
<div id="tabletennis" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('tabletennis')">&times;</span>
    
    <!-- Video -->
    <iframe 
      src="https://www.youtube.com/embed/SuJQdxP6HJc" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">VR Table Tennis</h3>

    <!-- Content Section -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>VR Table Tennis is an immersive, physics-accurate table tennis experience built for VR platforms. The core idea is to simulate the natural feel, responsiveness, and excitement of real-world ping pong using intuitive motion controls, accurate physics, and spatial audio.</p>
      </div>
      
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Single-Player Practice Mode</li>
          <li>Physics-based Ball Dynamics</li>
          <li>Spatial Audio Feedback</li>
          <li>VR Controller-based / Hand Tracking-based Racket Movement</li>
          <li>Score Tracking + Game Logic</li>
        </ul>
        <p>Prototype built within 1 week</p>
      </div>
      
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, Meta All-in-One SDK, and Meta XR Interaction Toolkit</p>
      </div>

      <div class="modal-section">
      </div>
    </div>
  </div>
</div> <!-- END of TT -->


<!-- VR Gun Game Modal -->
<div id="vrgungame" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('vrgungame')">&times;</span>
    
    <!-- Video -->
    <iframe 
      src="https://www.youtube.com/embed/qR7igsJuGhc" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">VR Gun Game</h3>

    <!-- Content Section -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>VR Gun Game is an interactive shooting range built in VR, where players practice aiming and hitting targets using a modular gun system. The project allows dynamic weapon customization by combining parts with different attributes (fire rate, impact force, ammo type, etc.).</p>
      </div>

      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>

      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Modular gun system with interchangeable parts</li>
          <li>Target shooting range for testing accuracy and performance</li>
          <li>Dynamic weapon attributes: fire rate, impact force, ammo type</li>
          <li>Physics-based interactions with rigidbodies</li>
          <li>Open-ended gameplay encouraging creative solutions</li>
        </ul>
      </div>

      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta All-in-One SDK, and Meta XR Interaction Toolkit</p>
      </div>
    </div>
  </div>
</div>




</div> <!-- END of .portfolio-grid -->


<!-- New Grid Section -->
<h2 style="text-align:center; color:#00ffcc; margin-top:60px; margin-bottom:20px;">
  XR Bootcamp Projects (Sole Developer)
</h2>

<div class="portfolio-grid">

  <!-- Project 1 -->
  <div class="project-card" onclick="openModal('project1')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/project1.png" alt="Project 1" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>StormBreaker (Thor’s Axe Replica)</h3>
    <p>Immersive VR throwing axe with natural spin, recall-to-hand, and impact embedding</p>
  </div>

  <!-- Project 2 -->
  <div class="project-card" onclick="openModal('project2')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/project2.png" alt="Project 2" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>Tin Can Toss – VR Game</h3>
    <p>Classic VR game challenge where players knock down cans with limited throws</p>
  </div>

  <!-- Project 3 -->
  <div class="project-card" onclick="openModal('project3')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/project3.png" alt="Project 3" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>Control Volume</h3>
    <p>Innovative VR control system using hand gestures to pilot & control a spaceship</p>
  </div>


  <!-- Project 4 -->
  <div class="project-card" onclick="openModal('project4')">
    <div class="project-image-container">
      <img src="/Web-Page/assets/images/project1.png" alt="Safe Cracking" class="project-image">
      <div class="overlay">
        <span class="plus">+</span>
      </div>
    </div>
    <h3>Safe Cracking</h3>
    <p>Immersive VR puzzle where players unlock a safe by rotating dials in the correct sequence</p>
  </div>

 <!-- Project 5 (Gravity Manipulation) -->
<div class="project-card" onclick="openModal('gravity')">
  <div class="project-image-container">
    <img src="/Web-Page/assets/images/project2.png" alt="Gravity Manipulation" class="project-image">
    <div class="overlay">
      <span class="plus">+</span>
    </div>
  </div>
  <h3>Gravity Manipulation</h3>
  <p>Interactive VR mechanic using push-pull forces to move and control objects in space</p>
</div>

<!-- Project 6 (Catching Fire) -->
<div class="project-card" onclick="openModal('projectFire')">
  <div class="project-image-container">
    <img src="/Web-Page/assets/images/project3.png" alt="Catching Fire" class="project-image">
    <div class="overlay">
      <span class="plus">+</span>
    </div>
  </div>
  <h3>Catching Fire</h3>
  <p>Interactive VR fire simulation with mechanics for ignition, spread, and extinguishing</p>
</div>


  <!-- Project 7 -->
<div class="project-card" onclick="openModal('project7')">
  <div class="project-image-container">
    <img src="/Web-Page/assets/images/project7.png" alt="Target Hunt VR" class="project-image">
    <div class="overlay">
      <span class="plus">+</span>
    </div>
  </div>
  <h3>Target Hunt – VR Shooting Gallery</h3>
  <p>Carnival style VR shooting game with scoring system</p>
</div>


  <!-- Project 7: Swinging Blades -->
<div class="project-card" onclick="openModal('swingingblades')">
  <div class="project-image-container">
    <img src="/Web-Page/assets/images/swingingblades.png" 
         alt="Swinging Blades VR" 
         class="project-image">
    <div class="overlay">
      <span class="plus">+</span>
    </div>
  </div>
  <h3>Swinging Blades – VR Obstacle Challenge</h3>
  <p>Animated swinging blades with teleport mechanics for obstacle evasion</p>
</div>


 <!-- Project 9: Debug Sandbox -->
<div class="project-card" onclick="openModal('project-debug-sandbox')">
  <div class="project-image-container">
    <img src="/Web-Page/assets/images/debugsandbox.png" 
         alt="Debug Sandbox VR" 
         class="project-image">
    <div class="overlay">
      <span class="plus">+</span>
    </div>
  </div>
  <h3>Interactive UI Control System – VR Sandbox</h3>
  <p>VR sandbox with dynamic UI panels for controlling lights, colors, materials, and gravity via player input.</p>
</div>



  

</div> <!-- END of portfolio-grid -->


<!-- 🔹 Modal for Project 1 -->
<div id="project1" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('project1')">&times;</span>
    
    <!-- Video -->
    <iframe width="560" height="315" src="https://www.youtube.com/embed/cpDL4y6sBUE" frameborder="0" allowfullscreen></iframe>

    <!-- Title -->
    <h3 class="modal-title">StormBreaker (Thor’s Axe Replica)</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Built a VR throwing axe inspired by Thor’s StormBreaker, featuring natural spin, realistic embedding, and recall-to-hand mechanics for immersive gameplay.</p>
      </div>
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Physics-based throwable axe with natural spin</li>
          <li>Embeds into walls and enemies on impact</li>
          <li>Recall mechanic via button press </li>
        </ul>
      </div>
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit, ProBuilder</p>
      </div>
    </div>
  </div>
</div>



<!-- 🔹 Modal for Project 2 -->
<div id="project2" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('project2')">&times;</span>
    
    <!-- Video -->
    <iframe width="560" height="315" src="https://www.youtube.com/embed/ispDiNu3H4s" frameborder="0" allowfullscreen></iframe>

    <!-- Title -->
    <h3 class="modal-title">Tin Can Toss – VR Game</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Developed a VR carnival game where players throw balls to knock down cans, with win/lose detection and automatic game reset mechanics.</p>
      </div>
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Interactive ball throwing with physics-based collisions</li>
          <li>Rigidbody-enabled cans that react realistically</li>
          <li>Win/lose detection with limited throws</li>
          <li>Automatic game reset system</li>
        </ul>
      </div>
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit, ProBuilder</p>
      </div>
    </div>
  </div>
</div>



<!-- 🔹 Modal for Project 3 -->
<div id="project3" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('project3')">&times;</span>
    
    <!-- Video -->
    <iframe width="560" height="315" src="https://www.youtube.com/embed/xDc444dvHvM" frameborder="0" allowfullscreen></iframe>

    <!-- Title -->
    <h3 class="modal-title">Control Volume – VR Spaceship Interaction</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Built an innovative VR interaction system that lets players control a spaceship using hand movements inside a designated control volume.</p>
      </div>
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Custom control volume requiring hand presence for activation</li>
          <li>Spaceship acceleration, deceleration, and rotation mapped to hand movement</li>
          <li>Support for tilt and roll based on hand gestures</li>
          <li>Button-press activation for immersive control</li>
        </ul>
      </div>
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit</p>
      </div>
    </div>
  </div>
</div>



<!-- 🔹 Modal for Project 4 -->
<div id="project4" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('project4')">&times;</span>
    
    <!-- Video -->
    <iframe width="560" height="315" src="https://www.youtube.com/embed/oh7enSJzgxE" frameborder="0" allowfullscreen></iframe>

    <!-- Title -->
    <h3 class="modal-title">Safe Cracking – VR Puzzle Interaction</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Developed a VR puzzle where players rotate a dial to unlock a safe by entering the correct combination, featuring realistic locking and unlocking mechanics.</p>
      </div>
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Interactive dial rotation with VR hand tracking</li>
          <li>Number counting system for left/right turns</li>
          <li>Locking and unlocking functionality</li>
          <li>Door opening mechanism after correct code entry</li>
        </ul>
      </div>
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit</p>
      </div>
    </div>
  </div>
</div>




<!-- 🔹 Modal for Gravity Manipulation -->
<div id="gravity" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('project5')">&times;</span>
    
    <!-- Video -->
    <iframe width="560" height="315" 
      src="https://www.youtube.com/embed/lJJvhNAL8-8" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">Gravity Manipulation – VR Physics Interaction</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Developed a VR system that allows players to manipulate objects using gravity-inspired push and pull devices. Each hand controls a plunger that pushes or pulls rigidbodies in the scene, enabling intuitive object movement, suspension, and placement in 3D space.</p>
      </div>

      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>

      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Dual plunger system for push/pull rigidbody manipulation</li>
          <li>Realistic force fields to suspend or reposition objects</li>
          <li>Physics-driven VR interactions for immersive gameplay</li>
          <li>Dynamic control combining both hands for precision placement</li>
        </ul>
      </div>

      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit, ProBuilder</p>
      </div>
    </div>
  </div>
</div>




<!-- 🔹 Modal for Project - Catching Fire -->
<div id="projectFire" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('project6')">&times;</span>
    
    <!-- Video -->
    <iframe width="560" height="315" 
      src="https://www.youtube.com/embed/O7R61cFFRUw" 
      frameborder="0" allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">Catching Fire – VR Fire Interaction System</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Designed an interactive VR fire simulation where players can ignite and extinguish objects, with fire spreading and fire mechanics for immersive gameplay.</p>
      </div>
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Fire source creation (torch, flame pit, flamethrower)</li>
          <li>Objects catch fire when brought near flames</li>
          <li>Extinguishing by immersing objects in water</li>
          <li>Dynamic fire spread across objects</li>
        </ul>
      </div>
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit, ProBuilder</p>
      </div>
    </div>
  </div>
</div>



<!-- 🔹 Modal for Project - Target Hunt -->
<div id="project7" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('project7')">&times;</span>
    
    <!-- Video -->
    <iframe width="560" height="315" 
      src="https://www.youtube.com/embed/YHpy6BfT2BE" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">Target Hunt – VR Shooting Gallery</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Developed a VR carnival-style shooting gallery where players use a virtual gun to hit moving targets, earning points based on accuracy. Includes win/lose logic, scoring system, and reset mechanics for replayability.</p>
      </div>

      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>

      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Physics-based shooting with grab-interactable gun</li>
          <li>Moving target system with dynamic difficulty</li>
          <li>Accuracy-based scoring with bonus points for center hits</li>
          <li>Reset system for automated or manual game restart</li>
          <li>Optional: Ammo and reloading mechanics</li>
        </ul>
      </div>

      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit</p>
      </div>
    </div>
  </div>
</div>





<!-- 🔹 Modal for Swinging Blades -->
<div id="swingingblades" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('swingingblades')">&times;</span>
    
    <!-- Video -->
    <iframe width="560" height="315" 
      src="https://www.youtube.com/embed/Zpx1sqAi3R4" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen>
    </iframe>

    <!-- Title -->
    <h3 class="modal-title">Swinging Blades – VR Obstacle Challenge</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Designed an interactive VR obstacle system with animated swinging blades using sinusoidal and ping-pong motion functions. Players must time their teleportation to avoid collisions, enhancing reflex-based gameplay.</p>
      </div>

      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>

      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Procedural blade motion using Mathf.Sin and Mathf.PingPong</li>
          <li>Collision detection with player for immersive danger feedback</li>
          <li>Integrated teleportation mechanics for obstacle evasion</li>
        </ul>
      </div>

      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit</p>
      </div>
    </div>
  </div>
</div>






<!-- 🔹 Modal for Debug Sandbox -->
<div id="project-debug-sandbox" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeModal('project-debug-sandbox')">&times;</span>
    
    <!-- Video -->
    <iframe src="https://www.youtube.com/embed/bBvtuFpZttM" allowfullscreen></iframe>

    <!-- Title -->
    <h3 class="modal-title">Debug Sandbox – Interactive UI Control System</h3>

    <!-- Details -->
    <div class="modal-details">
      <div class="modal-section">
        <h4>About</h4>
        <p>Designed a VR sandbox showcasing dynamic UI-driven scene manipulation. Players interact with on-screen UI panels to control lighting, colors, materials, and gravity in real time, while monitoring system performance through the Developer HUD overlay.</p>
      </div>
      <div class="modal-section">
        <h4>Role</h4>
        <p>Sole Developer</p>
      </div>
      <div class="modal-section">
        <h4>Core Mechanics / Highlights</h4>
        <ul>
          <li>Interactive VR UI for live scene adjustments</li>
          <li>Input-based control of lights, colors, materials, and gravity</li>
          <li>Performance monitoring integrated with Developer HUD</li>
        </ul>
      </div>
      <div class="modal-section">
        <h4>Tech Stack</h4>
        <p>Unity, C#, Meta XR Toolkit</p>
      </div>
    </div>
  </div>
</div>











  <!-- Add more projects as needed -->



<!-- About Section -->
<section id="about" class="about-section">
  <h2>About</h2>
  <p>Master’s in Engineering Design, IITM | Crafting VR Experiences with AI</p>
</section>


<!-- Skills Section -->
<section id="skills" class="skills-section">
  <h2>Skills</h2>
  <div class="skills-container">
    <span class="skill">VR Development</span>
    <span class="skill">Unity 3D</span>
    <span class="skill">C#</span>
    <span class="skill">Python</span>
    <span class="skill">C</span>
    <span class="skill">MatLab</span>
    <span class="skill">Ansys</span>
    <span class="skill">SAP MM/PP</span>
    <span class="skill">Fusion 360</span>
    <span class="skill">Machine Learning</span>
    <span class="skill">SQL</span>
    <span class="skill">Microsoft Office</span>
    <span class="skill">GitHub</span>
    <span class="skill">Problem solving</span>
    <span class="skill">Analytical mind</span>
  </div>
</section>




<!-- Resume Download Button -->
<a href="/Web-Page/assets/files/Javed_Akhter_Shaik_Resume.pdf" download class="resume-btn">Download Resume</a>


<!-- Contact Section -->
<section id="contact" class="contact-section">
  <h2>Contact</h2>
  <p>Feel free to reach out, I’d love to connect with you!</p>
  <p><b>Based in:</b> Chennai, India</p>
</section>


<footer>
  <a href="https://github.com/Javed-Akhter-Shaik" target="_blank">
  <img src="https://cdn-icons-png.flaticon.com/512/733/733553.png" alt="GitHub" width="30" height="30">
</a>

  <a href="https://www.linkedin.com/in/javed-akhter-shaik-76836320b/" target="_blank">
    <img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn" width="30" height="30">
  </a>
  <a href="mailto:shaikjaved672@gmail.com">
    <img src="https://cdn-icons-png.flaticon.com/512/732/732200.png" alt="Email" width="30" height="30">
  </a>
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
