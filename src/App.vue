<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)
const cvOpen = ref(false)

const skills = [
  {
    icon: '⌘',
    title: 'Programming',
    description: 'Programming fundamentals and web development.',
    items: ['C', 'C++', 'Python', 'HTML', 'CSS', 'JavaScript']
  },
  {
    icon: '⚙',
    title: 'Embedded Systems',
    description: 'Microcontrollers and hardware-based projects.',
    items: ['ESP32', 'Arduino', 'Raspberry Pi', 'PIC']
  },
  {
    icon: '◎',
    title: 'AI & Computer Vision',
    description: 'Image-based detection and intelligent systems.',
    items: ['YOLO', 'Computer Vision', 'Image Processing', 'Object Detection']
  },
  {
    icon: '⌁',
    title: 'Hardware & Electronics',
    description: 'Electronic circuits and connected devices.',
    items: ['Circuit Design', 'PCB Design', 'Sensors', 'IoT']
  }
]

const projects = [
  {
    number: '01',
    category: 'AI · Embedded Systems',
    title: 'SMART-TMS',
    subtitle: 'AI-Based Traffic Management System',
    description:
      'An AI-based traffic management system that uses computer vision for vehicle detection and counting, supporting dynamic traffic control based on traffic conditions.',
    technologies: [
      'Raspberry Pi 5',
      'ESP32-CAM',
      'ESP32',
      'YOLO',
      'Computer Vision'
    ],
    symbol: '⌁'
  },
  {
    number: '02',
    category: 'Automation · IoT',
    title: 'S.C.A.R.F',
    subtitle: 'Smart Classroom Automated and Reliable Fan',
    description:
      'An automated classroom fan system designed to control fan operation based on environmental conditions and classroom occupancy using sensors and an ESP32.',
    technologies: ['ESP32', 'Sensors', 'Automation', 'IoT'],
    symbol: '⚙'
  },
  {
    number: '03',
    category: 'Electronics · Hardware',
    title: 'Custom Regulated Power Supply',
    subtitle: 'Electronic Hardware Project',
    description:
      'A custom-designed regulated power supply developed to provide stable and controlled voltage output for electronic circuits and hardware projects.',
    technologies: [
      'Electronics',
      'Power Supply',
      'Circuit Design',
      'Hardware'
    ],
    symbol: 'ϟ'
  },
  {
    number: '04',
    category: 'Software · Database',
    title: 'Dental Clinic Management System',
    subtitle: 'Appointment and Record Management',
    description:
      'A system designed to manage dental clinic appointments and patient records, helping organize information and improve the efficiency of clinic operations.',
    technologies: [
      'Software Development',
      'Database',
      'System Design',
      'Records Management'
    ],
    symbol: '▤'
  },
  {
    number: '05',
    category: 'Embedded Systems · PCB',
    title: 'Custom PIC Development Board',
    subtitle: 'Microcontroller Development',
    description:
      'A custom development board designed for PIC microcontroller projects, providing a platform for programming, testing, and interfacing electronic components.',
    technologies: [
      'PIC Microcontroller',
      'Embedded Systems',
      'PCB Design',
      'Electronics'
    ],
    symbol: '⌘'
  }
]

const navigation = [
  { label: 'Home', href: '#home' },
  { label: 'About', href: '#about' },
  { label: 'Skills', href: '#skills' },
  { label: 'Projects', href: '#projects' },
  { label: 'Education', href: '#education' },
  { label: 'Certifications', href: '#certifications' },
  { label: 'Contact', href: '#contact' }
]

function closeMenu() {
  menuOpen.value = false
}

function toggleCV() {
  cvOpen.value = !cvOpen.value
}
</script>

<template>
  <div class="portfolio">
    <!-- NAVIGATION -->
    <header class="navbar">
      <a class="logo" href="#home" @click="closeMenu">
        Trisha<span>.</span>
      </a>

      <button
        class="menu-button"
        type="button"
        :aria-expanded="menuOpen"
        aria-label="Toggle navigation"
        @click="menuOpen = !menuOpen"
      >
        {{ menuOpen ? '✕' : '☰' }}
      </button>

      <nav :class="{ 'nav-open': menuOpen }">
        <a
          v-for="item in navigation"
          :key="item.href"
          :href="item.href"
          @click="closeMenu"
        >
          {{ item.label }}
        </a>

        <a class="nav-contact" href="#contact" @click="closeMenu">
          Let's Talk <span>↗</span>
        </a>
      </nav>
    </header>

    <main>
      <!-- HERO -->
      <section id="home" class="hero">
        <div class="hero-content">
          <div class="availability">
            <span class="status-dot"></span>
            COMPUTER ENGINEERING STUDENT
          </div>

          <p class="intro">Hello, I'm</p>

          <h1>Trisha Mae B. Mamuad</h1>

          <h2>
            Building skills.
            <span>Creating solutions.</span>
          </h2>

          <p class="hero-description">
            Interested in technology, programming, embedded systems,
            artificial intelligence, computer vision, and system development.
            I enjoy creating practical technology-based solutions to real-world
            problems and continuously improving my technical skills.
          </p>

          <div class="hero-buttons">
            <a class="btn primary-btn" href="#projects">
              Explore My Projects <span>↗</span>
            </a>

            <a class="btn secondary-btn" href="#contact">
              Contact Me
            </a>

            <div class="cv-dropdown">
              <button
                class="btn cv-btn"
                type="button"
                :aria-expanded="cvOpen"
                @click="toggleCV"
              >
                View CV <span>⌄</span>
              </button>

              <div v-if="cvOpen" class="cv-dropdown-menu">
                <a
                  href="/CV/MAMUAD_CV.png"
                  target="_blank"
                  rel="noopener noreferrer"
                  @click="cvOpen = false"
                >
                  ↗ View CV
                </a>

                <a
                  href="/CV/MAMUAD_CV.png"
                  download="MAMUAD_CV.png"
                  @click="cvOpen = false"
                >
                  ↓ Download CV
                </a>
              </div>
            </div>
          </div>

          <div class="hero-meta">
            <div>
              <span class="meta-icon">⌘</span>
              <span>Computer Engineering</span>
            </div>

            <div>
              <span class="meta-icon">⌖</span>
              <span>Cagayan, Philippines</span>
            </div>
          </div>
        </div>

        <div class="hero-visual">
          <div class="visual-glow"></div>
          <div class="orbit orbit-one"></div>
          <div class="orbit orbit-two"></div>

          <div class="profile-frame">
            <img
              src="/images/profile.jpg"
              alt="Portrait of Trisha Mae B. Mamuad"
            />
          </div>

          <div class="floating-card floating-top">
            <span class="floating-icon cyan-icon">⌘</span>
            <div>
              <strong>Problem Solver</strong>
              <small>Learn · Build · Improve</small>
            </div>
          </div>

          <div class="floating-card floating-bottom">
            <span class="floating-icon teal-icon">⚙</span>
            <div>
              <strong>Tech Enthusiast</strong>
              <small>Hardware & Software</small>
            </div>
          </div>

          <span class="decor decor-one">+</span>
          <span class="decor decor-two">+</span>
        </div>

        <a class="scroll-indicator" href="#about">
          <span></span>
          SCROLL TO EXPLORE
        </a>
      </section>

      <!-- ABOUT -->
      <section id="about" class="section">
        <div class="section-heading">
          <span class="eyebrow">GET TO KNOW ME</span>
          <h2>About <span>Me</span></h2>
          <p>A little about my journey, interests, and goals.</p>
        </div>

        <div class="about-layout">
          <div class="about-mark">
            <span class="about-bracket">&lt;</span>
            <span class="about-code">TM</span>
            <span class="about-bracket">/&gt;</span>
            <p>
              Learn with purpose.
              <br />
              Build with passion.
            </p>
          </div>

          <div class="about-content">
            <h3>Curious mind. <span>Practical solutions.</span></h3>

            <p>
              I am a motivated Computer Engineering student interested in
              system development, programming, networking, and emerging
              technologies. I enjoy applying my technical knowledge and
              problem-solving skills to build practical, reliable solutions.
            </p>

            <p>
              I seek hands-on experience to build my skills and contribute to
              real-world projects. I am adaptable, detail-oriented, eager to
              learn, and able to work independently or as part of a team.
            </p>

            <div class="about-highlights">
              <div>
                <span class="highlight-icon">✦</span>
                <span>Continuous Learning</span>
              </div>

              <div>
                <span class="highlight-icon">✦</span>
                <span>Problem Solving</span>
              </div>

              <div>
                <span class="highlight-icon">✦</span>
                <span>Team Collaboration</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- SKILLS -->
      <section id="skills" class="section section-alt">
        <div class="section-heading">
          <span class="eyebrow">WHAT I WORK WITH</span>
          <h2>Technical <span>Skills</span></h2>
          <p>Technologies and areas I am learning and working with.</p>
        </div>

        <div class="skills-container">
          <article
            v-for="skill in skills"
            :key="skill.title"
            class="skill-card"
          >
            <div class="skill-card-top">
              <span class="skill-icon">{{ skill.icon }}</span>
              <span class="card-arrow">↗</span>
            </div>

            <h3>{{ skill.title }}</h3>
            <p>{{ skill.description }}</p>

            <div class="skill-tags">
              <span v-for="item in skill.items" :key="item">
                {{ item }}
              </span>
            </div>
          </article>
        </div>
      </section>

      <!-- PROJECTS -->
      <section id="projects" class="section">
        <div class="section-heading">
          <span class="eyebrow">SELECTED WORK</span>
          <h2>Featured <span>Projects</span></h2>
          <p>Academic and technical projects that reflect my interests.</p>
        </div>

        <div class="projects-container">
          <article
            v-for="project in projects"
            :key="project.number"
            class="project-card"
          >
            <div class="project-visual">
              <span class="project-number">{{ project.number }}</span>
              <span class="project-symbol">{{ project.symbol }}</span>
              <span class="project-category">{{ project.category }}</span>
            </div>

            <div class="project-content">
              <p class="project-subtitle">{{ project.subtitle }}</p>
              <h3>{{ project.title }}</h3>
              <p class="project-description">{{ project.description }}</p>

              <div class="technologies">
                <span
                  v-for="technology in project.technologies"
                  :key="technology"
                >
                  {{ technology }}
                </span>
              </div>
            </div>
          </article>
        </div>

        <p class="projects-note">
          Academic projects and personal technical work.
        </p>
      </section>

      <!-- EDUCATION -->
      <section id="education" class="section section-alt">
        <div class="section-heading">
          <span class="eyebrow">MY ACADEMIC BACKGROUND</span>
          <h2>Education &amp; <span>Learning</span></h2>
          <p>Building a foundation in computing and engineering.</p>
        </div>

        <div class="education-container">
          <div class="timeline-line"></div>

          <article class="education-card">
            <div class="education-marker">01</div>

            <div>
              <span class="education-label">COLLEGE EDUCATION</span>
              <h3>Cagayan State University</h3>
              <h4>Bachelor of Science in Computer Engineering</h4>
              <p>College of Engineering and Architecture</p>
              <p class="education-location">
                Tuguegarao City, Cagayan, Philippines
              </p>
            </div>
          </article>
        </div>
      </section>

      <!-- CERTIFICATIONS AND SEMINARS -->
      <section id="certifications" class="section">
        <div class="section-heading">
          <span class="eyebrow">CONTINUOUS DEVELOPMENT</span>
          <h2>Certifications &amp; <span>Seminars</span></h2>
          <p>Learning opportunities related to technology and engineering.</p>
        </div>

        <div class="certifications-container single-certification">
          <article class="certification-card">
            <span class="certification-icon">✦</span>

            <div class="certification-content">
              <span class="education-label">SEMINARS &amp; CONFERENCES</span>
              <h3>
                Frontiers of Computer Engineering: 2025 International
                Conference on New and Emerging Technologies
              </h3>
            </div>

            <span class="certification-arrow">↗</span>
          </article>
        </div>
      </section>

      <!-- CONTACT -->
      <section id="contact" class="section section-alt">
        <div class="contact-panel">
          <div class="section-heading contact-heading">
            <span class="eyebrow">LET'S CONNECT</span>
            <h2>Have a project in <span>mind?</span></h2>
            <p>
              Feel free to reach out for collaboration, or
              technology-related conversations.
            </p>
          </div>

          <div class="contact-container">
            <a
              class="contact-card"
              href="mailto:trishamaemamuad05@email.com"
            >
              <span class="contact-icon">✉</span>
              <span class="contact-label">EMAIL</span>
              <strong>Send me an email</strong>
              <span class="contact-value">
                trishamaemamuad05@email.com
              </span>
            </a>

            <a class="contact-card" href="tel:09693583634">
              <span class="contact-icon">⌕</span>
              <span class="contact-label">PHONE</span>
              <strong>Give me a call</strong>
              <span class="contact-value">0969-358-3634</span>
            </a>

            <div class="contact-card">
              <span class="contact-icon">⌖</span>
              <span class="contact-label">LOCATION</span>
              <strong>Cagayan, Philippines</strong>
              <span class="contact-value">Angang, Tuao, Cagayan</span>
            </div>

            <a
              class="contact-card"
              href="https://github.com/trishamamuad"
              target="_blank"
              rel="noopener noreferrer"
            >
              <span class="contact-icon">⌘</span>
              <span class="contact-label">GITHUB</span>
              <strong>Explore my GitHub</strong>
              <span class="contact-value">
                github.com/trishamamuad ↗
              </span>
            </a>
          </div>
        </div>
      </section>
    </main>

    <!-- FOOTER -->
    <footer class="footer">
      <a class="logo footer-logo" href="#home">Trisha<span>.</span></a>

      <p>Designed and built by Trisha Mae B. Mamuad.</p>

      <p class="bible-verse">
        “Casting all your care upon him; for he careth for you.”
        <span>— 1 Peter 5:7</span>
      </p>

      <div class="footer-bottom">
        <span>© 2026 Trisha Mae B. Mamuad. All rights reserved.</span>
        <a href="#home">Back to top ↑</a>
      </div>
    </footer>
  </div>
</template>