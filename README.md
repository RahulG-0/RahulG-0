<h1 align="center">Rahul Gurukiran</h1>

<p align="center">
  Computer Science at the University of Toronto, class of 2027.<br>
  I build software across robotics, machine learning and full-stack web.
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/rahulgurukiran"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-rahulgurukiran-0A66C2?style=flat-square&logo=linkedin&logoColor=white"></a>
  <a href="mailto:rahul.gurukiran01@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Email-rahul.gurukiran01%40gmail.com-555555?style=flat-square&logo=gmail&logoColor=white"></a>
</p>

---

### What I'm doing now

- **Research assistant, Continuum Robotics Lab (University of Toronto).** Working on vision-language-action models for continuum robots.
- **Co-founder, [Vullpine](https://vullpine-waitlist.vercel.app/).** A web platform for agentic robot development, from design to simulation to deployment.
- **Previously:** Operations Engineer & AI Developer intern at CGI, on intelligent document processing for TD.

---

### Featured projects

<table>
  <tr>
    <td colspan="2" valign="top">
      <h4>Filling in the Missing Frame in Hand-Drawn Animation</h4>
      <p>Given two drawings from an animation, generate the one in between to double the frame rate. Animation is harder than video: outlines are a pixel or two wide, flat colour gives little to match, and parts jump far between drawings.</p>
      <ul>
        <li>Adapted a published interpolator (AMT) to hand-drawn animation (ATD-12K), with per-pixel optical flow from SEA-RAFT as extra input.</li>
        <li>Beats published AMT on unseen films, most on hard motion: <b>21.0 → 24.0 dB</b> PSNR.</li>
        <li>Found that plain fine-tuning quietly softens lines while PSNR hides it, and that a perceptual loss term fixes it.</li>
        <li>Evaluated with 3 seeds, paired bootstrap intervals, a line-distance metric built for animation and an unseen second source (Sakuga).</li>
        <li>I worked across the whole project, from the motion estimator and fine-tuning to training, evaluation and the write-up.</li>
      </ul>
      <p><b>Paper:</b> coming soon &nbsp;·&nbsp; <b>Code:</b> private, <a href="mailto:rahul.gurukiran01@gmail.com">demo on request</a></p>
      <p><img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"> <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white"> <img alt="OpenCV" src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white"></p>
    </td>
  </tr>
  <tr>
    <td colspan="2" valign="top">
      <h4>Mask-Aware Metric Depth Grounding for Transparent Objects</h4>
      <p>Depth cameras like the Intel RealSense fail on glass and clear plastic: light passes through, so the sensor reports a hole or, worse, the table behind the object. A grasp planner then reaches for a cup that isn't there. This project repairs that depth with no task-specific training, using only frozen foundation models and test-time optimization.</p>
      <ul>
        <li>Zero-shot transparent-object masks from Grounding DINO and SAM 2, using text prompts like "glass" and "plastic cup"</li>
        <li>A dense monocular depth prior from Depth Anything 3, grounded to metric scale using the trustworthy sensor pixels</li>
        <li>Key idea: exclude the corrupted sensor readings inside the mask before alignment, applied to both a global fit and the recent AnchorD optimizer (2026)</li>
        <li>Evaluating on TransCG (57k RGB-D images) and ClearGrasp, with oracle-mask and mask-perturbation studies to measure how segmentation quality affects depth accuracy</li>
      </ul>
      <p><b>Paper:</b> coming soon &nbsp;·&nbsp; <b>Code:</b> private, <a href="mailto:rahul.gurukiran01@gmail.com">demo on request</a></p>
      <p><img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"> <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white"> <img alt="JAX" src="https://img.shields.io/badge/JAX-A8B9CC?style=flat-square"> <img alt="SciPy" src="https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white"></p>
    </td>
  </tr>
  <tr>
    <td colspan="2" valign="top">
      <h4>Does Layout Matter? 2D Positional Encoding for Image-to-LaTeX</h4>
      <p>Formulas in PDFs, slides and scanned papers are stored as images, so they can't be edited, searched or read by screen readers. This project converts a formula image into the LaTeX that renders it. Math is two-dimensional (x<sup>2</sup> and x<sub>2</sub> differ only in vertical position), and recent models add 2D positional encodings for that reason, but always alongside other changes, so no one has measured what the encoding alone contributes.</p>
      <ul>
        <li>CNN encoder with residual blocks that turns the image into a feature grid, and a Transformer decoder that writes LaTeX tokens while attending to it</li>
        <li>Controlled ablation: the full model encodes each cell's row and column, the baseline is identical except for a flattened 1D index</li>
        <li>Trained on IM2LATEX-100K (~100k arXiv formulas), scored with BLEU, token edit distance and exact match</li>
        <li>Results broken down by structure (fractions, superscripts and subscripts, arrays) to show where layout information helps most</li>
        <li>I built the Transformer decoder and run the training experiments</li>
      </ul>
      <p><b>Paper:</b> coming soon &nbsp;·&nbsp; <b>Code:</b> private, <a href="mailto:rahul.gurukiran01@gmail.com">demo on request</a></p>
      <p><img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"> <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white"></p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/RahulG-0/docflow">DocFlow</a></h4>
      <p>Document processing pipeline. Classifies PDFs, extracts fields with an LLM, validates them, applies business rules and queues exceptions for human review. Includes a review console.</p>
      <p>
        <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
        <img alt="FastAPI" src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white">
        <img alt="Gemini API" src="https://img.shields.io/badge/Gemini_API-4285F4?style=flat-square&logo=google&logoColor=white">
        <img alt="Next.js" src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white">
      </p>
    </td>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/MananKakkar1/CadPilot">CadPilot</a> <sub>team project</sub></h4>
      <p>Agentic CAD: turns a written design brief into a validated, editable 3D model. I built the prompt-to-CAD agent page, the live build feed and the shared 3D viewer, with a team of four.</p>
      <p>
        <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white">
        <img alt="Next.js" src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white">
        <img alt="Gemini API" src="https://img.shields.io/badge/Gemini_API-4285F4?style=flat-square&logo=google&logoColor=white">
        <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white">
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/RahulG-0/vision-controlled-claw">Vision-Controlled Claw</a> <sub>work in progress</sub></h4>
      <p>Control a robotic claw with your hand. MediaPipe hand tracking measures how far each finger is curled and maps it to a servo angle. The live tracker drives a simulated five-finger claw on a 7-joint arm in ROS 2 and Gazebo, with a scripted pick-up demo. Driving the real claw's servos is in progress.</p>
      <a href="https://github.com/RahulG-0/vision-controlled-claw"><img alt="Tracked hand skeleton and the servo angle computed for each finger" src="https://raw.githubusercontent.com/RahulG-0/vision-controlled-claw/main/docs/hand_plot.png" width="100%"></a>
      <p>
        <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
        <img alt="MediaPipe" src="https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square&logo=google&logoColor=white">
        <img alt="OpenCV" src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white">
        <img alt="ROS 2" src="https://img.shields.io/badge/ROS_2-22314E?style=flat-square&logo=ros&logoColor=white">
      </p>
    </td>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/RahulG-0/drawbot">drawbot</a> <sub>simulation</sub></h4>
      <p>Pen plotter arm simulated in ROS 2 Jazzy and Gazebo Harmonic. Two NEMA 17 steppers drive a two-link arm and a servo lifts the pen. Includes inverse kinematics, stepper microstepping, and a command line tool that draws shapes or any polyline you publish.</p>
      <a href="https://github.com/RahulG-0/drawbot"><img alt="The demo sheet drawn in Gazebo" src="https://raw.githubusercontent.com/RahulG-0/drawbot/main/docs/demo.png" width="100%"></a>
      <p>
        <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
        <img alt="ROS 2" src="https://img.shields.io/badge/ROS_2-22314E?style=flat-square&logo=ros&logoColor=white">
        <img alt="Gazebo" src="https://img.shields.io/badge/Gazebo-FF6F00?style=flat-square">
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4>CopyCadder <sub>private</sub></h4>
      <p>Turns a 7-DOF Franka Emika Panda research arm into a handwriting robot. Type any text, in any font or format, and the arm writes it out on paper with a real pen.</p>
      <ul>
        <li>Converts rendered text into ordered pen strokes</li>
        <li>Plans the arm's motion for every stroke through a Python interface to the Panda</li>
        <li>Lifts and repositions the pen between strokes so letters and words come out clean</li>
      </ul>
      <p><b>Code:</b> private, <a href="mailto:rahul.gurukiran01@gmail.com">demo on request</a></p>
      <p>
        <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
      </p>
    </td>
    <td width="50%" valign="top">
      <h4>Unix Shell <sub>private</sub></h4>
      <p>A Unix shell built from scratch in C, using only system calls for process control.</p>
      <ul>
        <li>Pipelines of any length (<code>cmd1 | cmd2 | cmd3</code>)</li>
        <li>Input and output redirection (<code>&lt;</code>, <code>&gt;</code>)</li>
        <li>Background processes with <code>&amp;</code>, plus job control (<code>jobs</code>, <code>fg</code>)</li>
        <li>Signal handling, so Ctrl+C stops the running job instead of the shell</li>
        <li>Built-in commands alongside running external programs via <code>fork</code> and <code>exec</code></li>
      </ul>
      <p><b>Code:</b> private, <a href="mailto:rahul.gurukiran01@gmail.com">demo on request</a></p>
      <p>
        <img alt="C" src="https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black">
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/RahulG-0/outfit-ai">OutfitPicker</a></h4>
      <p>Outfit recommender. Embeds photos of your wardrobe with a pretrained CNN, then ranks pairings by category, colour harmony and style similarity.</p>
      <p>
        <img alt="TensorFlow" src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white">
        <img alt="FastAPI" src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white">
        <img alt="Next.js" src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white">
        <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white">
      </p>
    </td>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/RahulG-0/pathfinding-stuffs">Pathfinding</a></h4>
      <p>Interactive A* visualizer. Draw a start, an end and walls on a grid, then watch the search find the shortest path.</p>
      <p>
        <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
        <img alt="Pygame" src="https://img.shields.io/badge/Pygame-3776AB?style=flat-square">
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/RahulG-0/PA_A_SECLUDED_PLACE">A Secluded Place</a></h4>
      <p>Audio-driven horror game. You can't see the monster, so you locate it by sound and defend through a quick-time event. Built with a teammate in high school.</p>
      <p>
        <img alt="Java" src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white">
        <img alt="Swing" src="https://img.shields.io/badge/Swing-5382A1?style=flat-square">
      </p>
    </td>
  </tr>
</table>

**Also:** [ML and AI experiments](https://github.com/RahulG-0/ML_and_AI), a neural network written from scratch in NumPy.

---

### Tools

<p>
  <img alt="C" src="https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black">
  <img alt="C++" src="https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white">
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
  <img alt="Java" src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white">
  <br>
  <img alt="ROS" src="https://img.shields.io/badge/ROS-22314E?style=flat-square&logo=ros&logoColor=white">
  <img alt="OpenCV" src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white">
  <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white">
  <img alt="TensorFlow" src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white">
  <img alt="NumPy" src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white">
  <br>
  <img alt="React" src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB">
  <img alt="Next.js" src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white">
  <img alt="Node.js" src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white">
  <img alt="FastAPI" src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white">
</p>
