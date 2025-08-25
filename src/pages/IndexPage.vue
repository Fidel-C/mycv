<!-- eslint-disable @typescript-eslint/no-unused-vars -->
<template>
  <div id="home" class="portfolio-container">
    <!-- Hero Section -->
    <section class="hero-section">
      <div class="hero-content">
        <div class="hero-text">
          <div class="greeting">
            <span class="wave">👋</span>
            <h1>Hi, I'm Fidel C.</h1>
          </div>
          <div class="role-container">
            <h2 class="role-text">Full-stack Software Developer</h2>
            <div class="role-highlight"></div>
          </div>
          <p class="hero-description">
            Bridging the gap between legal expertise and cutting-edge technology
          </p>
          <div class="hero-actions">
            <button class="btn-primary" @click="scrollToSection('about')">
              <span>Learn More</span>
              <i class="arrow-icon">→</i>
            </button>
            <button class="btn-secondary" @click="scrollToSection('contact')">
              <span>Get In Touch</span>
            </button>
          </div>
        </div>
        <div class="hero-image">
          <div class="image-container">
            <img src="/profile.png" alt="Fidel C." class="profile-image" />
            <div class="image-glow"></div>
          </div>
        </div>
      </div>
      <div class="scroll-indicator" @click="scrollToSection('about')">
        <span>Scroll Down</span>
        <div class="scroll-arrow">↓</div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">About Me</h2>
          <div class="section-subtitle">
            Where law meets technology
          </div>
        </div>
        
        <div class="about-content">
          <div class="about-text">
            <div class="about-card">
              <h3>Background & Education</h3>
              <p>
                With a Law degree (LLB) and BL qualification, I've carved a unique path 
                specializing in areas where technology and legal expertise intersect, 
                including intellectual property and cybersecurity.
              </p>
            </div>
            
            <div class="about-card">
              <h3>The Journey</h3>
              <p>
                Though without a formal CS degree, my passion for technology led me 
                to explore coding as a hobby. What started as weekend projects has 
                evolved into a comprehensive skill set in full-stack development.
              </p>
            </div>
            
            <div class="about-card">
              <h3>Professional Expertise</h3>
              <p>
                I excel in designing intuitive user interfaces, crafting scalable 
                backend architectures, and ensuring seamless integration. My legal 
                background ensures compliance with regulations and privacy standards.
              </p>
            </div>
          </div>
          
          <div class="stats-grid">
            <div class="stat-card">
              <div class="stat-number">5+</div>
              <div class="stat-label">Years Experience</div>
            </div>
            <div class="stat-card">
              <div class="stat-number">50+</div>
              <div class="stat-label">Projects Completed</div>
            </div>
            <div class="stat-card">
              <div class="stat-number">100%</div>
              <div class="stat-label">Client Satisfaction</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Technical Expertise</h2>
          <div class="section-subtitle">
            Technologies I work with
          </div>
        </div>
        
        <div class="skills-grid">
          <div class="skill-category">
            <h3>Frontend</h3>
            <div class="skill-tags">
              <span class="skill-tag">HTML</span>
              <span class="skill-tag">CSS</span>
              <span class="skill-tag">JavaScript</span>
              <span class="skill-tag">TypeScript</span>
              <span class="skill-tag">Vue.js</span>
              <span class="skill-tag">React/Next</span>
              <span class="skill-tag">Kivy & Flet</span>
          <span class="skill-tag">Flutter Basics</span>
            </div>
          </div>
          
          <div class="skill-category">
            <h3>Backend</h3>
            <div class="skill-tags">
              <span class="skill-tag">Python</span>
              <span class="skill-tag">FastAPI</span>
              <span class="skill-tag">Django</span>
              <span class="skill-tag">Nodejs</span>
              <span class="skill-tag">Laravel </span>
             <span class="skill-tag">Java Basics</span>
              
            </div>
          </div>
          
          <div class="skill-category">
            <h3>Mobile & Desktop</h3>
            <div class="skill-tags">
              <span class="skill-tag">Flutter</span>
              <span class="skill-tag">Dart</span>
              <span class="skill-tag">PWA</span>
              <span class="skill-tag">Electron</span>
            </div>
          </div>
          
          <div class="skill-category">
            <h3>Tools & Database</h3>
            <div class="skill-tags">
              <span class="skill-tag">Git</span>
              <span class="skill-tag">Supabase</span>
              <span class="skill-tag">PostgreSQL</span>
              <span class="skill-tag">MongoDB</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Featured Projects</h2>
          <div class="section-subtitle">
            Some of my recent work
          </div>
        </div>
        
        <div class="projects-grid">
          <div 
            v-for="project in featuredProjects" 
            :key="project.id"
            class="project-card"
            @click="openProjectModal(project)"
          >
            <div class="project-image">
              <img :src="project.image" :alt="project.title" />
              <div class="project-overlay">
                <button class="view-project-btn">
                  <span>View Details</span>
                  <i class="arrow-icon">→</i>
                </button>
              </div>
            </div>
            <div class="project-content">
              <h3>{{ project.title }}</h3>
              <p>{{ project.description }}</p>
              <div class="project-tech">
                <span 
                  v-for="tech in project.tech" 
                  :key="tech"
                  class="tech-tag"
                >
                  {{ tech }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Let's Work Together</h2>
          <div class="section-subtitle">
            Ready to bring your ideas to life
          </div>
        </div>
        
        <div class="contact-content">
          <div class="contact-info">
            <div class="contact-item">
              <div class="contact-icon">📧</div>
              <div class="contact-details">
                <h4>Email</h4>
                <a href="mailto:fidelchukwunyere@gmail.com">
                  fidelchukwunyere@gmail.com
                </a>
              </div>
            </div>
            
            <div class="contact-item">
              <div class="contact-icon">💼</div>
              <div class="contact-details">
                <h4>LinkedIn</h4>
                <a href="#" target="_blank">
                  Fidel Chukwunyere
                </a>
              </div>
            </div>
            
            <div class="contact-item">
              <div class="contact-icon">💬</div>
              <div class="contact-details">
                <h4>WhatsApp</h4>
                <a href="https://wa.me/+2347064620806" target="_blank">
                  +234 706 462 0806
                </a>
              </div>
            </div>
          </div>
          
          <div class="contact-form">
            <form @submit.prevent="sendMessage">
              <div class="form-group">
                <input 
                  v-model="form.name" 
                  type="text" 
                  placeholder="Your Name"
                  required
                />
              </div>
              <div class="form-group">
                <input 
                  v-model="form.email" 
                  type="email" 
                  placeholder="Your Email"
                  required
                />
              </div>
              <div class="form-group">
                <textarea 
                  v-model="form.message" 
                  placeholder="Your Message"
                  rows="5"
                  required
                ></textarea>
              </div>
              <button type="submit" class="btn-primary full-width">
                <span>Send Message</span>
                <i class="arrow-icon">→</i>
              </button>
            </form>
          </div>
        </div>
      </div>
    </section>

    <!-- Project Modal -->
    <div v-if="selectedProject" class="modal-overlay" @click="closeProjectModal">
      <div class="modal-content" @click.stop>
        <button class="modal-close" @click="closeProjectModal">×</button>
        
        <div class="modal-header">
          <img :src="selectedProject.image" :alt="selectedProject.title" />
          <div class="modal-title">
            <h2>{{ selectedProject.title }}</h2>
            <p>{{ selectedProject.description }}</p>
          </div>
        </div>
        
        <div class="modal-body">
          <div class="features-list">
            <h3>Key Features</h3>
            <ul>
              <li v-for="feature in selectedProject.features" :key="feature">
                {{ feature }}
              </li>
            </ul>
          </div>
          
          <div class="tech-stack">
            <h3>Tech Stack</h3>
            <div class="tech-tags">
              <span 
                v-for="tech in selectedProject.tech" 
                :key="tech"
                class="tech-tag"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
        
        <div class="modal-footer">
          <a 
            v-if="selectedProject.url" 
            :href="selectedProject.url" 
            target="_blank"
            class="btn-primary"
          >
            <span>View Live Demo</span>
            <i class="arrow-icon">→</i>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'

// Reactive data
const selectedProject = ref(null)
const form = ref({
  name: '',
  email: '',
  message: ''
})

// Featured projects data
const featuredProjects = ref([

  {
    title: 'Real Estate Management App',
    url: 'https://realestate-mp0n.onrender.com',
    image:'realestate.png',
    features: [
      'Real Estate Listings',
      '3DView for listiings',
      'Map View for listing',
      'Inquiry feature with email',
      'User authentication and authorization,etc',
    ],
  },
  {
    title: 'School Management System',
    url: 'https://onqode-school.onrender.com',
    image:'school-manage.png',
    features: [
      'Django Backend',
      'Session Authentication',
      'OTP 2Factor Authentication',
      'CSV files to db records',
      'Realtime Notifications',
      'User can manage booking from user dashboard',
      'Srudents can download School Fees Invoice/Receipts',
      'User can optionally mark notification as read',
      'Admin can send special notifivation to user or to all users',
    ],
  },

  {
    title: 'Ecommerce Store PWA/Mobile App',
    url: 'https://onqode-store.netlify.app',
    image:'ecommerce.png',
    features: [
      'Admin Panel to manage products and orders',
      'User can search for available products',
      'User can add product to cart',
      'User can decrease or increase quantity of products in cart',
      'User can make order and pay for products',
    ],
  },
   {
    title: 'Medical Appointment Booking',
    url: '',
    image:'medical.png',
    features: [
      'Admin Panel to manage appointments, patients and staff',
      'Separate dashboard for doctors, admins and patients.',
      'Book or cancel medical appointments easily',
      'Automated payment integration',
      'Email Notification of each transaction and booking status',

    ],
  },
  {
    title: 'VTU Web App',
    url: 'https://mobiledata.onrender.com',
    image:'vtu.jpg',
    features: [
      'Admin Panel to manage products and orders',
      'Purchase airtime, data and more...',
      'User can manage wallet from user dashboard',
      'Email Notification of each purchase',
      'User can optionally download receipts from dashboard as PDF',
      'Notifications',
    ],
  },
  {
    title: 'VTU PWA/Mobile App',
    url: 'https://mobiledata.netlify.app',
    image:'vtu-mini.png',
    features: [
      'Admin panel to manage products and orders',
      'No registration or Login Required',
      'Apk available at Amazon Appstore',
      'Purchase airtime, data more',
      'Email Notification of each purchase',
      'Notifications',
    ],
  }
  ,
  {
    title: 'Food Delivery App',
    url: '',
    image:'resto.jpeg',
    features: [
      'Admin Panel to manage inventory and orders',
      'Place order on assorted meals easily',
      'Automated payment integration',
      'Email Notification of each transaction and order status',

    ],
  },
   {
     title:'Scribe Kit Ai',
    url:'https://scribekitai.netlify.app',
     image:'scribekitai.jpg',
     features:[
       '20+ collection of custom made AI tools',
       'Payment gateway integration',
       'Admin Panel',
       'Document generation',
       'Academic games',
       'Ai powdered exams and tests',
       'Passwordless login',
       'Virtual Wallet management',
       'Time based pass management',
       'International payment management',
       'Spreadsheets and Excel Automation, etc']
   },

    {
     title:'Quizkid Ai',
    url:'https://quizkid.netlify.app',
     image:'quizkid.jpg',
     features:[
       'Collection of custom made AI tools for quizzes, exams, interviews and learning.',
       'Payment gateway integration',
       'Admin Panel',
       'Suitable for kids',
       'Academic games',
       'Ai powdered exams and tests'
       'Virtual Wallet management',
       'Time based pass management',
       'International payment management',
 ]
   },

          {
     title:'Chatlegal Ai',
    url:'https://chatlegal.netlify.app',
     image:'chatlegal.jpg',
     features:[
       'Legal Ai Assistant for Lawyers(Hallucination-free)',
       'Payment gateway integration',
       'Admin Panel',
       'Suitable for lawyers and other professionals',
       'Academic and Legal Research',
       'Compliance test and fact checking'
       'Virtual Wallet management',
       'Time based pass management',
       'International payment management',
 ]
   } ,
  
  {
    title: 'Flight Booking PWA',
    url: 'https://onqode-booking.netlify.app',
    image:'flight.png',
    features: [
      'FastApi Backend',
      'JWT Authentication',
      'Sign-up Email verification',
      'Realtime Push Notifications by admin',
      'User can manage booking from user dashboard',
      'User can download flight Ticket as PDF',
      'User can optionally mark notification as read',
      'Admin can send special email to user or a mass mail to all users',
    ],
  },
])

// Methods
const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const openProjectModal = (project: any) => {
  selectedProject.value = project
  document.body.style.overflow = 'hidden'
}

const closeProjectModal = () => {
  selectedProject.value = null
  document.body.style.overflow = 'auto'
}

const sendMessage = () => {
  // Handle form submission
  console.log('Form submitted:', form.value)
  // Reset form
  form.value = { name: '', email: '', message: '' }
  alert('Message sent successfully!')
}

</script>

<style scoped>
/* Global Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.portfolio-container {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: #333;
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

/* Hero Section */
.hero-section {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.hero-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><defs><radialGradient id="a" cx="50%" cy="50%" r="50%"><stop offset="0%" stop-color="%23ffffff" stop-opacity="0.1"/><stop offset="100%" stop-color="%23ffffff" stop-opacity="0"/></radialGradient></defs><circle cx="200" cy="200" r="150" fill="url(%23a)"/><circle cx="800" cy="300" r="100" fill="url(%23a)"/><circle cx="400" cy="700" r="200" fill="url(%23a)"/></svg>');
  animation: float 20s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-20px); }
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 1;
}

.hero-text {
  color: white;
}

.greeting {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.wave {
  font-size: 2rem;
  animation: wave 2s ease-in-out infinite;
}

@keyframes wave {
  0%, 100% { transform: rotate(0deg); }
  25% { transform: rotate(20deg); }
  75% { transform: rotate(-20deg); }
}

.greeting h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin: 0;
}

.role-container {
  position: relative;
  margin-bottom: 2rem;
}

.role-text {
  font-size: 2rem;
  font-weight: 600;
  background: linear-gradient(45deg, #fff, #f0f0f0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.role-highlight {
  height: 4px;
  background: linear-gradient(45deg, #ff6b6b, #ffd93d);
  border-radius: 2px;
  margin-top: 0.5rem;
  animation: expand 2s ease-out;
}

@keyframes expand {
  from { width: 0; }
  to { width: 100%; }
}

.hero-description {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.hero-actions {
  display: flex;
  gap: 1rem;
}

.btn-primary, .btn-secondary {
  padding: 1rem 2rem;
  border: none;
  border-radius: 50px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
}

.btn-primary {
  background: linear-gradient(45deg, #ff6b6b, #ffd93d);
  color: white;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 20px rgba(255, 107, 107, 0.3);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.1);
  color: white;
  border: 2px solid rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

.arrow-icon {
  font-style: normal;
  transition: transform 0.3s ease;
}

.btn-primary:hover .arrow-icon,
.btn-secondary:hover .arrow-icon {
  transform: translateX(4px);
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-container {
  position: relative;
}

.profile-image {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  border: 4px solid rgba(255, 255, 255, 0.2);
  object-fit: cover;
  position: relative;
  z-index: 2;
}

.image-glow {
  position: absolute;
  top: -20px;
  left: -20px;
  right: -20px;
  bottom: -20px;
  background: linear-gradient(45deg, #ff6b6b, #ffd93d, #4ecdc4, #45b7d1);
  border-radius: 50%;
  z-index: 1;
  opacity: 0.3;
  animation: rotate 10s linear infinite;
}

@keyframes rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  color: white;
  text-align: center;
  cursor: pointer;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
  40% { transform: translateX(-50%) translateY(-10px); }
  60% { transform: translateX(-50%) translateY(-5px); }
}

.scroll-arrow {
  font-size: 1.5rem;
  margin-top: 0.5rem;
}

/* Section Styles */
.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 1rem;
  background: linear-gradient(45deg, #667eea, #764ba2);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-subtitle {
  font-size: 1.2rem;
  color: #666;
}

/* About Section */
.about-section {
  padding: 6rem 0;
  background: #f8f9fa;
}

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  align-items: start;
}

.about-text {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.about-card {
  background: white;
  padding: 2rem;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.about-card:hover {
  transform: translateY(-5px);
}

.about-card h3 {
  color: #667eea;
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

.stats-grid {
  display: grid;
  gap: 2rem;
}

.stat-card {
  background: white;
  padding: 2rem;
  border-radius: 20px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.stat-number {
  font-size: 3rem;
  font-weight: 700;
  color: #667eea;
  margin-bottom: 0.5rem;
}

.stat-label {
  color: #666;
  font-size: 1rem;
}

/* Skills Section */
.skills-section {
  padding: 6rem 0;
  background: white;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.skill-category {
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 20px;
  text-align: center;
}

.skill-category h3 {
  color: #667eea;
  margin-bottom: 1.5rem;
  font-size: 1.5rem;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  justify-content: center;
}

.skill-tag {
  background: linear-gradient(45deg, #667eea, #764ba2);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 25px;
  font-size: 0.9rem;
  font-weight: 500;
}

/* Projects Section */
.projects-section {
  padding: 6rem 0;
  background: #f8f9fa;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.project-card {
  background: white;
  border-radius: 20px;
  overflow: hidden;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.project-image {
  position: relative;
  height: 200px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.1);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(102, 126, 234, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.view-project-btn {
  background: white;
  color: #667eea;
  padding: 1rem 2rem;
  border: none;
  border-radius: 50px;
  font-weight: 600;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  transform: translateY(20px);
  transition: transform 0.3s ease;
}

.project-card:hover .view-project-btn {
  transform: translateY(0);
}

.project-content {
  padding: 2rem;
}

.project-content h3 {
  color: #333;
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

.project-content p {
  color: #666;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tech-tag {
  background: #e9ecef;
  color: #667eea;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 500;
}

/* Contact Section */
.contact-section {
  padding: 6rem 0;
  background: white;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  background: #f8f9fa;
  border-radius: 15px;
  transition: transform 0.3s ease;
}

.contact-item:hover {
  transform: translateY(-2px);
}

.contact-icon {
  font-size: 2rem;
  width: 60px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(45deg, #667eea, #764ba2);
  border-radius: 50%;
}

.contact-details h4 {
  color: #333;
  margin-bottom: 0.5rem;
}

.contact-details a {
  color: #667eea;
  text-decoration: none;
  transition: color 0.3s ease;
}

.contact-details a:hover {
  color: #764ba2;
}

.contact-form {
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 20px;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 1rem;
  border: 2px solid #e9ecef;
  border-radius: 10px;
  font-size: 1rem;
  transition: border-color 0.3s ease;
  background: white;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #667eea;
}

.full-width {
  width: 100%;
  justify-content: center;
}

/* Modal Styles */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  padding: 2rem;
}

.modal-content {
  background: white;
  border-radius: 20px;
  max-width: 800px;
  width: 100%;
  max-height: 90vh;
  overflow-y: auto;
  position: relative;
  animation: slideIn 0.3s ease-out;
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(50px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.modal-close {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: none;
  border: none;
  font-size: 2rem;
  cursor: pointer;
  color: #666;
  z-index: 10;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: all 0.3s ease;
}

.modal-close:hover {
  background: #f8f9fa;
  color: #333;
}

.modal-header {
  position: relative;
}

.modal-header img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 20px 20px 0 0;
}

.modal-title {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
  color: white;
  padding: 3rem 2rem 2rem;
  border-radius: 0 0 20px 20px;
}

.modal-title h2 {
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.modal-title p {
  font-size: 1.1rem;
  opacity: 0.9;
}

.modal-body {
  padding: 2rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
}

.features-list h3,
.tech-stack h3 {
  color: #667eea;
  margin-bottom: 1rem;
  font-size: 1.3rem;
}

.features-list ul {
  list-style: none;
  padding: 0;
}

.features-list li {
  padding: 0.5rem 0;
  position: relative;
  padding-left: 1.5rem;
  color: #666;
}

.features-list li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #667eea;
  font-weight: bold;
}

.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.modal-footer {
  padding: 2rem;
  border-top: 1px solid #e9ecef;
  display: flex;
  justify-content: flex-end;
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 2rem;
  }
  
  .hero-text {
    order: 2;
  }
  
  .hero-image {
    order: 1;
  }
  
  .greeting h1 {
    font-size: 2.5rem;
  }
  
  .role-text {
    font-size: 1.5rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .stats-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
  }
  
  .stat-number {
    font-size: 2rem;
  }
  
  .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .projects-grid {
    grid-template-columns: 1fr;
  }
  
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .modal-body {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .hero-actions {
    flex-direction: column;
    align-items: center;
  }
  
  .btn-primary,
  .btn-secondary {
    width: 100%;
    max-width: 300px;
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 1rem;
  }
  
  .greeting h1 {
    font-size: 2rem;
  }
  
  .role-text {
    font-size: 1.2rem;
  }
  
  .hero-description {
    font-size: 1rem;
  }
  
  .stats-grid {
    grid-template-columns: 1fr;
  }
  
  .profile-image {
    width: 200px;
    height: 200px;
  }
  
  .modal-overlay {
    padding: 1rem;
  }
  
  .modal-title h2 {
    font-size: 1.5rem;
  }
  
  .modal-body {
    padding: 1rem;
  }
}

/* Smooth scrolling for the entire page */
html {
  scroll-behavior: smooth;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(45deg, #667eea, #764ba2);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(45deg, #764ba2, #667eea);
}

/* Loading animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.about-card,
.skill-category,
.project-card,
.contact-item {
  animation: fadeInUp 0.6s ease-out;
}

/* Hover effects for better interactivity */
.skill-tag:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(102, 126, 234, 0.3);
}

.tech-tag:hover {
  background: #667eea;
  color: white;
}

/* Focus styles for accessibility */
.btn-primary:focus,
.btn-secondary:focus,
.form-group input:focus,
.form-group textarea:focus {
  outline: 2px solid #667eea;
  outline-offset: 2px;
}

/* Print styles */
@media print {
  .hero-section {
    background: white !important;
    color: black !important;
  }
  
  .btn-primary,
  .btn-secondary {
    display: none;
  }
  
  .modal-overlay {
    display: none;
  }
}

</style>
