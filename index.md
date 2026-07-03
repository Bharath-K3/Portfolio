---
layout: default
---

<style>
  /* Timeline News Section */
  .timeline {
    position: relative;
    padding-left: 24px;
    margin: 25px 0;
    border-left: 2px solid #e2e8f0;
  }
  
  .timeline-item {
    position: relative;
    margin-bottom: 24px;
  }
  
  .timeline-item::before {
    content: "";
    position: absolute;
    left: -31px;
    top: 5px;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: #2563eb;
    border: 2px solid #ffffff;
    box-shadow: 0 0 0 2px #93c5fd;
    transition: all 0.25s ease;
  }
  
  .timeline-item:hover::before {
    transform: scale(1.3);
    background-color: #1d4ed8;
  }
  
  .timeline-date {
    font-weight: 700;
    color: #2563eb;
    font-size: 0.85em;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 3px;
  }
  
  .timeline-content {
    font-size: 0.95em;
    color: #334155;
    line-height: 1.5;
  }
  
  .timeline-content em {
    font-weight: 600;
    font-style: italic;
  }

  /* Publications Cards */
  .pub-list {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .pub-card {
    padding: 18px;
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.02);
    transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
  }
  
  .pub-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 16px -4px rgba(0, 0, 0, 0.06), 0 4px 6px -2px rgba(0, 0, 0, 0.04);
    border-color: #cbd5e1;
  }
  
  .pub-title {
    font-size: 1.05em;
    font-weight: 600;
    color: #0f172a;
    margin-bottom: 6px;
    line-height: 1.4;
    font-family: 'Outfit', sans-serif;
  }
  
  .pub-authors {
    font-size: 0.9em;
    color: #475569;
    margin-bottom: 6px;
  }
  
  .pub-authors strong {
    color: #0f172a;
    font-weight: 600;
  }
  
  .pub-venue {
    font-size: 0.88em;
    font-style: italic;
    color: #64748b;
    margin-bottom: 12px;
  }
  
  .pub-links {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }
  
  .pub-link {
    display: inline-flex;
    align-items: center;
    padding: 4px 10px;
    background: #f1f5f9;
    color: #475569 !important;
    border-radius: 6px;
    font-size: 0.8em;
    font-weight: 500;
    border: 1px solid #e2e8f0;
    text-decoration: none !important;
    transition: all 0.2s ease;
  }
  
  .pub-link:hover {
    background: #2563eb;
    color: #ffffff !important;
    border-color: #2563eb;
    box-shadow: 0 2px 4px rgba(37, 99, 235, 0.15);
  }

  /* Collapsible / Details Summary slider styling */
  details {
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    background: #f8fafc;
    margin: 20px 0;
    transition: all 0.3s ease;
    overflow: hidden;
  }
  
  details[open] {
    background: #ffffff;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    border-color: #cbd5e1;
  }
  
  summary {
    font-weight: 600;
    color: #334155;
    cursor: pointer;
    outline: none;
    user-select: none;
    font-family: 'Outfit', sans-serif;
    font-size: 1em;
    padding: 14px 18px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: background 0.2s ease;
  }
  
  summary:hover {
    color: #2563eb;
    background: #f1f5f9;
  }

  summary::after {
    content: "▼";
    font-size: 0.8em;
    color: #64748b;
    transition: transform 0.2s ease;
  }

  details[open] summary::after {
    transform: rotate(-180deg);
    color: #2563eb;
  }

  /* Hide default marker */
  details summary::-webkit-details-marker {
    display: none;
  }
  details summary {
    list-style: none;
  }

  .details-content {
    padding: 18px;
    border-top: 1px solid #e2e8f0;
    background: #ffffff;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  /* Certifications Styles */
  .cert-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin: 15px 0;
  }
  
  .cert-card {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 14px 18px;
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.02);
    transition: all 0.25s ease;
  }
  
  .cert-card:hover {
    border-color: #cbd5e1;
    transform: translateY(-1px);
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.04);
  }
  
  .cert-logo {
    width: 42px;
    height: 42px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 0.9em;
    flex-shrink: 0;
    box-shadow: inset 0 -2px 0 rgba(0,0,0,0.1);
    font-family: 'Outfit', sans-serif;
  }
  
  .logo-stanford { background: #fee2e2; color: #8c1515; border: 1px solid #fca5a5; }
  .logo-deeplearning { background: #fef3c7; color: #d97706; border: 1px solid #fde68a; }
  .logo-ibm { background: #dbeafe; color: #0f62fe; border: 1px solid #bfdbfe; }
  .logo-google { background: #e0f2fe; color: #0284c7; border: 1px solid #bae6fd; }
  .logo-michigan { background: #fef3c7; color: #00274c; border: 1px solid #fde68a; }
  .logo-uci { background: #dcfce7; color: #15803d; border: 1px solid #bbf7d0; }

  .cert-details {
    flex-grow: 1;
  }
  
  .cert-name {
    font-weight: 600;
    color: #0f172a;
    font-size: 0.95em;
    line-height: 1.3;
  }
  
  .cert-issuer {
    font-size: 0.85em;
    color: #475569;
    margin-top: 2px;
  }
  
  .cert-meta {
    font-size: 0.8em;
    color: #64748b;
    margin-top: 4px;
    display: flex;
    gap: 12px;
    align-items: center;
  }
  
  .cert-btn {
    padding: 4px 10px;
    font-size: 0.78em;
    font-weight: 500;
    background: #f1f5f9;
    color: #475569 !important;
    border: 1px solid #e2e8f0;
    border-radius: 4px;
    text-decoration: none !important;
    transition: all 0.2s ease;
    flex-shrink: 0;
  }
  
  .cert-btn:hover {
    background: #2563eb;
    color: #ffffff !important;
    border-color: #2563eb;
  }
</style>

I am a PhD Student in Computer Science at the University of North Texas, working under the supervision of Dr. Ajita Rattani at the Visual Computing and Biometric Security Lab (VCBSL). My research focuses on the intersection of Generative AI, computer vision, and biometric security, specifically deepfake synthesis/analysis, diffusion transformers, and adversarial robustness in facial and ocular biometrics. Previously, I completed my MS in Artificial Intelligence with a 4.0 GPA and held research roles at the Indian Institute of Science (IISc) and IIIT-Bangalore.

---

## Recent Achievements

<div class="timeline">
  <!-- 1. CVPR -->
  <div class="timeline-item">
    <div class="timeline-date">June 2026</div>
    <div class="timeline-content">
      Our paper <em>MMFace-DiT: A Dual-Stream Diffusion Transformer for High-Fidelity Multimodal Face Generation</em> has been accepted to the prestigious <strong>CVPR 2026</strong> conference in Denver, Colorado.
    </div>
  </div>

  <!-- 2. ICASSP -->
  <div class="timeline-item">
    <div class="timeline-date">May 2026</div>
    <div class="timeline-content">
      Presented our work <em>VoxMorph: Scalable Zero-Shot Voice Identity Morphing via Disentangled Embeddings</em> at the <strong>ICASSP 2026</strong> (IEEE International Conference on Acoustics, Speech and Signal Processing) conference in Barcelona, Spain.
    </div>
  </div>

  <!-- 3. Interspeech -->
  <div class="timeline-item">
    <div class="timeline-date">June 2026</div>
    <div class="timeline-content">
      Our paper <em>Exploiting Neural Audio Codec Latents for Adversarial Audio Attacks</em> has been accepted at the <strong>Interspeech 2026</strong> conference in Sydney, Australia.
    </div>
  </div>

  <!-- NSF I-Corps -->
  <div class="timeline-item">
    <div class="timeline-date">December 2025</div>
    <div class="timeline-content">
      Our NEXBIS team received the <strong>NSF I-Corps Award</strong> for <em>"The Present and Accounted For"</em>, in support of our solution addressing contactless and privacy-preserving biometrics. The groundbreaking work was led by Entrepreneurial Lead <strong>Bharath Krishnamurthy</strong>, Technical Lead Dr. Ajita Rattani, and Industrial Mentor Terry Chapas.
    </div>
  </div>

  <!-- 4. DOOMGAN -->
  <div class="timeline-item">
    <div class="timeline-date">July 2025</div>
    <div class="timeline-content">
      Our work <em>DOOMGAN: High-Fidelity Dynamic Identity Obfuscation Ocular Generative Morphing</em> has been accepted at the <strong>IJCB 2025</strong> (IEEE International Joint Conference on Biometrics) conference.
    </div>
  </div>

  <!-- 5. Neurocomputing -->
  <div class="timeline-item">
    <div class="timeline-date">2025</div>
    <div class="timeline-content">
      Two research papers, <em>ABRobOcular: Adversarial benchmarking and robustness analysis of datasets and tools for ocular-based user recognition</em> and <em>Analyzing and mitigating bias of facial attribute classifiers using ChatGPT</em>, have been accepted for publication in the <strong>Neurocomputing</strong> journal.
    </div>
  </div>
</div>

---

## Publications

<div class="pub-list">

  <!-- MMFace-DiT -->
  <div class="pub-card">
    <div class="pub-title">MMFace-DiT: A Dual-Stream Diffusion Transformer for High-Fidelity Multimodal Face Generation</div>
    <div class="pub-authors"><strong>B. Krishnamurthy</strong>, A. Rattani</div>
    <div class="pub-venue">Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), 2026.</div>
    <div class="pub-links">
      <a class="pub-link" href="https://openaccess.thecvf.com/content/CVPR2026/html/Krishnamurthy_MMFace-DiT_A_Dual-Stream_Diffusion_Transformer_for_High-Fidelity_Multimodal_Face_Generation_CVPR_2026_paper.html" target="_blank">Paper</a>
      <a class="pub-link" href="https://github.com/Bharath-K3/MMFace-DiT" target="_blank">Code</a>
      <a class="pub-link" href="https://vcbsl.github.io/MMFace-DiT/" target="_blank">Project Page</a>
    </div>
  </div>

  <!-- VoxMorph -->
  <div class="pub-card">
    <div class="pub-title">VoxMorph: Scalable Zero-Shot Voice Identity Morphing via Disentangled Embeddings</div>
    <div class="pub-authors"><strong>B. Krishnamurthy</strong>, A. Rattani</div>
    <div class="pub-venue">IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), 2026.</div>
    <div class="pub-links">
      <a class="pub-link" href="https://arxiv.org/abs/2601.20883" target="_blank">PDF</a>
      <a class="pub-link" href="https://github.com/Bharath-K3/VoxMorph" target="_blank">Code</a>
      <a class="pub-link" href="https://vcbsl.github.io/VoxMorph/" target="_blank">Project Page</a>
    </div>
  </div>

  <!-- Audio Attack -->
  <div class="pub-card">
    <div class="pub-title">Exploiting Neural Audio Codec Latents for Adversarial Audio Attacks</div>
    <div class="pub-authors">S. Bhattacharya, <strong>B. Krishnamurthy</strong>, A. Rattani</div>
    <div class="pub-venue">Interspeech, 2026.</div>
    <div class="pub-links">
      <a class="pub-link" href="https://arxiv.org/abs/2606.20893" target="_blank">PDF</a>
      <a class="pub-link" href="https://github.com/VCBSL/DAC-GAN" target="_blank">Code</a>
    </div>
  </div>

  <!-- DOOMGAN -->
  <div class="pub-card">
    <div class="pub-title">DOOMGAN: High-Fidelity Dynamic Identity Obfuscation Ocular Generative Morphing</div>
    <div class="pub-authors"><strong>B. Krishnamurthy</strong>, A. Rattani</div>
    <div class="pub-venue">IEEE International Joint Conference on Biometrics (IJCB), 2025.</div>
    <div class="pub-links">
      <a class="pub-link" href="https://arxiv.org/abs/2507.17158" target="_blank">PDF</a>
      <a class="pub-link" href="https://github.com/Bharath-K3/DOOMGAN" target="_blank">Code</a>
    </div>
  </div>

  <!-- ABRobOcular -->
  <div class="pub-card">
    <div class="pub-title">ABRobOcular: Adversarial benchmarking and robustness analysis of datasets and tools for ocular-based user recognition</div>
    <div class="pub-authors"><strong>B. Krishnamurthy</strong>, A. Rattani</div>
    <div class="pub-venue">Neurocomputing, 640, 130352, 2025.</div>
    <div class="pub-links">
      <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S0925231225004072" target="_blank">PDF</a>
      <a class="pub-link" href="https://github.com/Bharath-K3/ABRobOcular" target="_blank">Code</a>
    </div>
  </div>

</div>

<details>
  <summary>More Publications</summary>
  <div class="details-content">
    
    <!-- ChatGPT Bias -->
    <div class="pub-card">
      <div class="pub-title">Analyzing and mitigating bias of facial attribute classifiers using ChatGPT</div>
      <div class="pub-authors">A. Manzoor, <strong>B. Krishnamurthy</strong>, A. Rattani</div>
      <div class="pub-venue">Neurocomputing, 650, 130825, 2025.</div>
      <div class="pub-links">
        <a class="pub-link" href="https://www.sciencedirect.com/science/article/abs/pii/S0925231225010240" target="_blank">Paper</a>
      </div>
    </div>

    <!-- Multi-Task Segment -->
    <div class="pub-card">
      <div class="pub-title">Simultaneous segmentation of multiple structures in fundal images using multi-tasking deep neural networks</div>
      <div class="pub-authors">S. K. Vengalil, <strong>B. Krishnamurthy</strong>, N. Sinha</div>
      <div class="pub-venue">Frontiers in Signal Processing, 2, 936875, 2023.</div>
    </div>

  </div>
</details>

---

## Experience

- **University of North Texas** | Graduate Research & Teaching Assistant | 2023 – Present
  - Conducting core research on generative modeling (GANs, Diffusion Transformers) for facial/ocular biometrics and digital vulnerability discovery at VCBSL.
  - Served as Teaching Assistant for advanced computer science courses, including CSCE 5215 (Introduction to Machine Learning).

- **International Institute of Information Technology, Bangalore (IIIT-B)** | Research Assistant | 2021 – 2022
  - Engineered a multi-tasking deep learning architecture for medical fundus image analysis, achieving 98% accuracy in blood vessel and optic disc segmentation.
  - Improved exudate segmentation dice scores by 15% and achieved a 12x acceleration in inference speed relative to baseline standalone models.

- **Indian Institute of Science (IISc)** | Research Intern (Video Analytics Lab) | Jan 2021 – Apr 2021
  - Developed texturing and rendering pipelines for 3D human dataset creation using Blender and its Python API.
  - Integrated Skinned Multi-Person Linear (SMPL) models with PyTorch/NumPy for downstream 3D human pose recovery and estimation models.

---

## Education

- **PhD in Computer Science** | University of North Texas | *In Progress*
- **MS in Artificial Intelligence** | University of North Texas | **GPA: 4.0 / 4.0**
- **B.E. in Electronics and Communication Engineering** | Ambedkar Institute of Technology (VTU) | 2020

---

## Certifications

<div class="cert-list">

  <!-- 1. Stanford ML -->
  <div class="cert-card">
    <div class="cert-logo logo-stanford">SU</div>
    <div class="cert-details">
      <div class="cert-name">Machine Learning</div>
      <div class="cert-issuer">Stanford University</div>
      <div class="cert-meta">
        <span>Issued Aug 2019</span>
        <span>•</span>
        <span>Credential ID: <code class="cert-meta-id">K69SPCM4QXWG</code></span>
      </div>
    </div>
    <a class="cert-btn" href="https://www.coursera.org/account/accomplishments/verify/K69SPCM4QXWG" target="_blank">Show Credential</a>
  </div>

  <!-- 2. TensorFlow Developer -->
  <div class="cert-card">
    <div class="cert-logo logo-deeplearning">DL</div>
    <div class="cert-details">
      <div class="cert-name">TensorFlow Developer</div>
      <div class="cert-issuer">DeepLearning.AI</div>
      <div class="cert-meta">
        <span>Issued Nov 2019</span>
      </div>
    </div>
    <a class="cert-btn" href="https://www.coursera.org/account/accomplishments/professional-cert/ML5GYQPHVFJ7?utm_source=link&utm_medium=certificate&utm_content=cert_image&utm_campaign=sharing_cta&utm_product=prof" target="_blank">Show Credential</a>
  </div>

  <!-- 3. IBM AI Engineering -->
  <div class="cert-card">
    <div class="cert-logo logo-ibm">IBM</div>
    <div class="cert-details">
      <div class="cert-name">AI Engineering</div>
      <div class="cert-issuer">IBM</div>
      <div class="cert-meta">
        <span>Issued May 2020</span>
      </div>
    </div>
    <a class="cert-btn" href="https://www.coursera.org/account/accomplishments/professional-cert/KTL5F8TV7BAH" target="_blank">Show Credential</a>
  </div>

  <!-- 4. Google IT Automation -->
  <div class="cert-card">
    <div class="cert-logo logo-google">G</div>
    <div class="cert-details">
      <div class="cert-name">Google IT Automation with Python</div>
      <div class="cert-issuer">Google</div>
    </div>
    <a class="cert-btn" href="https://www.coursera.org/account/accomplishments/professional-cert/FAYHVDCS5EVH" target="_blank">Show Credential</a>
  </div>

  <!-- 5. Python For Everybody -->
  <div class="cert-card">
    <div class="cert-logo logo-michigan">U-M</div>
    <div class="cert-details">
      <div class="cert-name">Python For Everybody</div>
      <div class="cert-issuer">University of Michigan</div>
    </div>
    <a class="cert-btn" href="https://www.coursera.org/account/accomplishments/specialization/RHX9S5493HJ6" target="_blank">Show Credential</a>
  </div>

</div>

<details>
  <summary>More Certifications</summary>
  <div class="details-content">
    
    <!-- 6. UCI IoT -->
    <div class="cert-card">
      <div class="cert-logo logo-uci">UCI</div>
      <div class="cert-details">
        <div class="cert-name">Internet of Things (IOT)</div>
        <div class="cert-issuer">University of California, Irvine - The Paul Merage School of Business</div>
      </div>
      <a class="cert-btn" href="https://www.coursera.org/account/accomplishments/specialization/G3PGFKWDDRSH" target="_blank">Show Credential</a>
    </div>

    <!-- 7. IBM Python for Data Science -->
    <div class="cert-card">
      <div class="cert-logo logo-ibm">IBM</div>
      <div class="cert-details">
        <div class="cert-name">Python for Data Science</div>
        <div class="cert-issuer">IBM</div>
      </div>
      <a class="cert-btn" href="https://www.credly.com/badges/17db8d94-a5eb-4560-98f5-c3829290167c/linked_in_profile" target="_blank">Show Credential</a>
    </div>

  </div>
</details>

---

## Technical Skills

- **Core Areas**: Generative Adversarial Networks (GANs), Diffusion Models (DiTs, LDM), Computer Vision, Biometric Security, Adversarial Machine Learning.
- **Frameworks & Tools**: PyTorch, TensorFlow, NumPy, Blender API, Git, Docker.

---

## Technical Writing

Selected technical deep-dives and tutorials authored on [Paperspace](https://blog.paperspace.com/author/bharath/) and [Medium](https://bharath-k1297.medium.com/), focusing on machine translation, sequence-to-sequence architectures, DCGANs, and SRGAN implementations.
