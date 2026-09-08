<script setup>
import { ref } from 'vue'

// 1. The reactive variable that controls the tabs
const activeTab = ref('backend')

// 2. Your skills data
const skillCategories = [

  {
    id: 'backend',
    title: 'Backend & Programming',
    skills: ['Python', 'PHP', 'MySQL & PostgreSQL', 'Firebase']
  },
  {
    id: 'analytics',
    title: 'Data Analytics',
    skills: ['PowerBI', 'Pandas', 'Microsoft Excel', 'DBeaver']
  },
  {
    id: 'frontend',
    title: 'Frontend & UI',
    skills: ['HTML5', 'CSS3', 'JavaScript', 'Vue.js', 'React', 'Bootstrap', 'Figma', 'Adobe XD']
  },
   {
    id: 'cybersec',
    title: 'Cybersecurity',
    skills: ['Metasploit Framework', 'Metasploitable', 'OpenSSL', 'Kali Linux', 'Ubuntu Linux', 'Windows OS']
  },


  {
    id: 'tools',
    title: 'Cloud, DevOps & Virtualization',
    skills: ['Docker', 'Git', 'Oracle VirtualBox', 'Azure', 'AWS']
  }
]
</script>

<template>
  <div class="home-container">
    
    <section id="home" class="hero-section">
      
      <img src="/python_img.png" alt="" class="floating-icon icon-1 d-none d-lg-block">
      <img src="/powerBI_icon.png" alt="" class="powerBI-icon icon-2 d-none d-lg-block">
      <img src="/docker_icon.png" alt="" class="docker-icon icon-3 d-none d-lg-block">
      <img src="/python_img.png" alt="" class="floating-icon icon-4 d-none d-lg-block">

      <img src="/photo_2026-09-08_14-53-29.jpg" alt="" class="floating-icon icon-6 d-none d-lg-block">
      <img src="/photo_2026-09-08_14-53-32.jpg" alt="" class="floating-icon icon-5 d-none d-lg-block">
      
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-name">Hi, I'm Ashley Wong</h1>
          <p class="hero-subtitle">Aspiring Data Analyst</p>
          
          <div class="contact-info">
            <a href="mailto:ashley.wjm@gmail.com" class="contact-link">
              <span class="contact-icon">✉️</span> ashley.wjm@gmail.com
            </a>
            <a href="https://www.linkedin.com/in/ashley-wong-997b77216" target="_blank" class="contact-link">
              <span class="contact-icon">🔗</span> LinkedIn
            </a>
          </div>
          
          <a href="/WJMASHLEY_Resume.pdf" download="Ashley_Wong_Resume.pdf" class="download-resume-btn text-decoration-none mt-2">
            <span>📄</span> Here's my resume
          </a>
        </div>
        
        <div class="hero-image">
          <img src="/my_image.png" alt="Ashley Wong" class="profile-img">
        </div>
      </div>
    </section>

    <section id="about" class="section about-section">
      <div class="about-container shadow-sm">
        <h2 class="about-title">About Me</h2>
        <p class="about-text">
          Hello! I am a Year 3 Information Systems student at SMU. I am passionate about exploring the possibilities of data analytics to make data-driven decisions.
        </p>
        <p class="about-text">
          Whether I am building web applications, designing customer retention models, or diving into vulnerability research, I love tackling complex technical challenges. Outside of my studies, I am always looking for new ways to grow as a developer and security professional.
        </p>
      </div>
    </section>

    <section id="projects" class="section projects-section" style="padding: 4rem 2rem;">
      <h2 class="section-title">Projects</h2>
      <p style="text-align: center; color: #994d47;">Add your projects content here</p>
    </section>

    <section id="skills" class="section skills-section">
      <h2 class="section-title">Technical Skills</h2>

      <div class="folder-container shadow-sm">
        
        <div class="folder-tabs">
          <button
            v-for="category in skillCategories"
            :key="category.id"
            @click="activeTab = category.id"
            :class="['folder-tab', { active: activeTab === category.id }]"
          >
            {{ category.title }}
          </button>
        </div>

        <div class="folder-body">
          <div class="folder-content">
            <ul class="skill-tags">
              <li
                v-for="(skill, index) in skillCategories.find(c => c.id === activeTab)?.skills"
                :key="index"
                class="skill-tag shadow-sm"
              >
                {{ skill }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section id="experience" class="section">
      <h2 class="section-title">Experience</h2>
      <p style="text-align: center; color: #994d47;">Add your experience content here</p>
    </section>

    <section id="education" class="section">
      <h2 class="section-title">Education</h2>
      <p style="text-align: center; color: #994d47;">Add your education content here</p>
    </section>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Mrs+Saint+Delafield&display=swap'); 

/* Main Layout & Colors */
.home-container {
  position: relative;
  min-height: 100vh;
  background-color: #e6e5d5; 
  color: #994d47; 
  padding: 0;
  margin: 0;
  font-family: system-ui, -apple-system, sans-serif;
}

/* ========================================= */
/* HERO SECTION & ICONS                      */
/* ========================================= */
.hero-section {
  min-height: 90vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  position: relative; 
  overflow: hidden;
}

.hero-content {
  max-width: 1200px;
  width: 100%;
  display: grid;
  grid-template-columns: 0.6fr 1fr;
  gap: 0.5rem;
  align-items: flex-start;
  position: relative;
  z-index: 10; /* Keeps text above icons */
}

.hero-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-left: 3rem;
}

.hero-name {
  font-family: 'Mrs Saint Delafield', cursive;
  font-size: 6rem;
  font-weight: 400;
  margin: 0 0 0.5rem 0;
  color: #994d47;
  line-height: 1.1;
}

.hero-subtitle {
  font-size: 1.5rem;
  color: #994d47;
  margin: 0 0 2rem 0;
  font-weight: 600;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-bottom: 2rem;
}

.contact-link {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  color: #994d47;
  text-decoration: none;
  font-size: 1.05rem;
  font-weight: 500;
  transition: all 0.3s ease;
}

.contact-link:hover {
  opacity: 0.6;
  transform: translateX(5px);
}

.download-resume-btn {
  align-self: flex-start;
  background: #994d47;
  color: #e6e5d5; 
  border: none;
  padding: 0.9rem 2rem;
  border-radius: 25px;
  font-weight: 600;
  font-size: 1rem;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.download-resume-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(153, 77, 71, 0.3);
  color: #ffffff;
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.profile-img {
  width: 100%;
  max-width: 400px;
  height: auto;
  border-radius: 10px;
  object-fit: cover;
  box-shadow: 0 10px 30px rgba(153, 77, 71, 0.15);
}

/* Floating Icons */
.floating-icon, .powerBI-icon, .docker-icon {
  position: absolute;
  z-index: 1; 
  pointer-events: none; 
}
.icon-1 { top: 10%; right: 5%; transform: rotate(-15deg); width: 80px; }
.icon-2 { top: 60%; left: 40%; transform: rotate(20deg); width: 100px; }
.icon-3 { top: 15%; left: 30%; transform: rotate(-5deg); width: 50px; }
.icon-4 { top: 92%; left: 2%; transform: rotate(10deg); width: 80px; }

.icon-5 { top: 80%; left: 45%; transform: rotate(15deg); width: 90px; }
.icon-6 { top: 70%; right: 8%; transform: rotate(-20deg); width: 130px; }

/* ========================================= */
/* ABOUT SECTION                             */
/* ========================================= */
.about-section {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 60vh; 
  padding: 4rem 2rem;
}

.about-container {
  background-color: rgba(255, 255, 255, 0.5); 
  max-width: 1000px;
  width: 100%;
  padding: 4rem;
  border-radius: 20px;
  text-align: center;
  border: 1px solid rgba(153, 77, 71, 0.15); 
}

.about-title {
  font-family: 'Playfair Display', serif;
  font-size: 3rem;
  color: #994d47;
  margin-bottom: 1.5rem;
}

.about-text {
  font-size: 1.15rem;
  line-height: 1.8;
  color: #994d47;
  opacity: 0.9;
  margin-bottom: 1rem;
}

/* ========================================= */
/* FOLDER SKILLS SECTION                     */
/* ========================================= */
.skills-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 4rem 2rem;
  min-height: 80vh;
}

.section-title {
  font-family: 'Playfair Display', serif;
  font-size: 3rem;
  color: #994d47;
  margin-bottom: 2rem;
  text-align: center;
}

.folder-container {
  width: 100%;
  max-width: 900px;
  margin: 0 auto;
}

.folder-tabs {
  display: flex;
  gap: 0.3rem;
  margin-bottom: -2px; 
}

.folder-tab {
  background-color: rgba(255, 255, 255, 0.3);
  color: #994d47;
  border: 1px solid rgba(153, 77, 71, 0.2);
  border-bottom: none;
  padding: 1rem 1.8rem;
  border-radius: 15px 15px 0 0; 
  font-family: system-ui, -apple-system, sans-serif;
  font-weight: 600;
  font-size: 1.05rem;
  cursor: pointer;
  transition: all 0.2s ease;
  opacity: 0.7;
  position: relative;
  z-index: 1;
}

.folder-tab:hover {
  background-color: rgba(255, 255, 255, 0.5);
  opacity: 1;
}

.folder-tab.active {
  background-color: rgba(255, 255, 255, 0.65);
  opacity: 1;
  z-index: 3;
  padding-bottom: 1.2rem;
}

.folder-body {
  background-color: rgba(255, 255, 255, 0.65);
  border: 1px solid rgba(153, 77, 71, 0.2);
  border-radius: 0 20px 20px 20px; 
  padding: 3.5rem;
  position: relative;
  z-index: 2;
  min-height: 250px;
}

.folder-content {
  animation: fadeIn 0.3s ease-out; 
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(5px); }
  to { opacity: 1; transform: translateY(0); }
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  list-style: none;
  padding: 0;
  margin: 0;
}

.skill-tag {
  background-color: #994d47;
  color: #e6e5d5;
  padding: 0.8rem 1.5rem;
  border-radius: 30px;
  font-size: 1.1rem;
  font-weight: 500;
  letter-spacing: 0.5px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.skill-tag:hover {
  transform: translateY(-3px);
  box-shadow: 0 5px 15px rgba(153, 77, 71, 0.3);
}

/* ========================================= */
/* MOBILE RESPONSIVENESS                     */
/* ========================================= */
@media (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }
  
  .hero-text { align-items: center; padding-left: 0; }
  .contact-info { align-items: center; }
  .download-resume-btn { align-self: center; }
  .hero-name { font-size: 4rem; }
  .profile-img { max-width: 300px; }
  
  .folder-tabs {
    flex-wrap: nowrap;
    overflow-x: auto; 
    -webkit-overflow-scrolling: touch;
  }
  
  .folder-tab {
    white-space: nowrap; 
    font-size: 0.95rem;
    padding: 0.8rem 1.2rem;
  }
  
  .folder-body {
    border-radius: 0 0 20px 20px; 
    padding: 2rem 1.5rem;
  }
}
</style>