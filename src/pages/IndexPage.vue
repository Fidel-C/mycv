<!-- Full upgraded landing page with CSS, JavaScript logic and floating 3D icons -->
<!-- Full upgraded landing page with floating 3D icons, full content and projects -->
<template>
  <q-page id="home">
    <!-- Top Section -->
    <div class="column bg-primary q-pa-md full-screen items-center justify-center" style="min-height: 60vh; position: relative; overflow: hidden">
      <div v-for="icon in floatingIcons" :key="icon.id" :style="icon.style" class="floating-icon">
        <q-icon :name="icon.name" size="xl" class="text-accent" />
      </div>

      <div class="column col-12 col-md-8 justify-center text-center animate__animated animate__fadeInDown">
        <div class="text-grey text-h5 q-mt-xl">Hi</div>
        <div data-aos="fade-right" data-aos-duration="1000" class="text-accent text-h4 q-my-lg" id="about">I am Fidel C.</div>
        <div data-aos="fade-left" data-aos-duration="1000" class="text-accent text-h6">A Full-stack Software Developer</div>

        <div class="row q-my-md justify-center">
          <q-btn v-if="!showDetails" color="secondary" flat icon="more" label="Read More About Me" @click="showDetails = true" />
          <q-btn v-if="showDetails" color="secondary" flat icon="password" label="Hide Details" @click="showDetails = false" />
        </div>

        <q-img :src="'/profile.png'" spinner-color="accent" style="height: 150px; max-width: 150px; border-radius: 50%; border-top: 5px dotted #f2f4f7; border-bottom: 3px dotted #f2f4f7; border-left: 2px dotted #e43a19; margin: 2rem auto;" />
      </div>

      <div class="row justify-around text-center q-mt-md">
        <div class="text-bold text-accent column">Email: <span class="text-grey">fidelchukwunyere@gmail.com</span></div>
        <div class="text-bold text-accent column">Linkedin: <span class="text-grey">Fidel Chukwunyere</span></div>
        <q-btn color="secondary" text-color="accent" label="Hire Me" @click="scrollToTarget('contact')" icon="fa fa-briefcase" class="q-mt-sm" />
      </div>
    </div>

    <q-dialog v-model="showDetails">
      <q-card class="bg-primary text-accent q-pa-md">
        <q-scroll-area style="height: 70vh">
          <div class="text-body2 text-italic q-mt-md" v-html="bioContent"></div>
        </q-scroll-area>
        <q-card-actions align="right">
          <q-btn flat label="Close" color="secondary" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <div class="q-mt-xl q-pa-md">
      <div class="text-primary text-h5 text-center text-bold">My Tech Skills</div>
      <div class="row q-gutter-md justify-center q-mt-md animate__animated animate__pulse animate__infinite">
        <q-card v-for="tech in techIcons" :key="tech.name" flat class="bg-white q-pa-md text-center shadow-2" style="width: 80px; height: 80px; border-radius: 20px">
          <q-img :src="tech.src" :alt="tech.name" style="width: 40px; height: 40px; margin: auto" />
          <div class="text-caption q-mt-xs">{{ tech.name }}</div>
        </q-card>
      </div>
    </div>

    <!-- Projects Section -->
    <div class="q-mt-xl q-pa-md" id="projects">
      <div class="text-center text-h5 text-bold text-primary">Some of My Projects</div>
      <q-table
        :rows="projectRows"
        :rows-per-page-options="[12, 15, 20]"
        :rows-per-page="10"
        grid
      >
        <template #item="project">
          <q-card class="my-card q-ma-md q-my-xl q-mx-auto" style="height: min-content; width: 300px; border-radius: 30px; box-shadow: 5px 5px #111F4D;">
            <q-img
              :src="project.row.image"
              :ratio="16/9"
              spinner-color="primary"
              spinner-size="82px"
              style="width: 100%; height: auto; border-top-right-radius: 30px; border-top-left-radius: 30px;"
            >
              <div class="absolute-bottom text-bold text-subtitle1 text-center">{{ project.row.title }}</div>
            </q-img>
            <q-card-actions class="row q-mt-auto">
              <q-btn no-caps flat label="View Details" class="text-primary text-center q-mx-auto" @click="handleProjectDetails(project.row)" />
            </q-card-actions>
          </q-card>
        </template>
      </q-table>
    </div>

    <!-- Contact Section -->
    <div class="q-mt-xl q-pa-md text-center" id="contact">
      <div class="text-bold text-h5 text-primary">Contact Me</div>
      <div class="row q-pa-md justify-evenly animate__animated animate__pulse animate__infinite">
        <a href="mailto:fidelchukwunyere@gmail.com" target="_blank" class="has-text-light">
          <q-icon name="mdi-gmail" size="lg" class="text-red" />
        </a>
        <a href="https://wa.me/+2347064620806" target="_blank" class="has-text-light">
          <q-icon name="mdi-whatsapp" class="text-green" size="lg" />
        </a>
        <a href="https://m.me/febuka1" target="_blank" class="has-text-light">
          <q-icon name="facebook" size="lg" />
        </a>
      </div>
    </div>
  </q-page>
</template>


<script setup>
import { ref, onMounted } from 'vue';

const showDetails = ref(false);
const bioContent = ref(`
  <p>I bring a blend of legal expertise and a fervent passion for coding and technology. With a background in law and a deep interest in tech, I've built innovative software solutions.</p>
  <p>Education: LLB, BL. Now pursuing a career intersecting law and tech (IP, Cybersecurity).</p>
  <p>Stack: Fullstack development (Frontend & Backend), Legal-Tech systems, scalable platforms.</p>
  <p>Skills include: React, Vue, Node.js, Next.js, Express.js, Django, Flutter, Supabase, Git, TypeScript, JavaScript, PHP, Python, Dart, Java (fundamentals), etc.</p>
`);

const projectRows = ref([
  {
    title: 'Real Estate Management App',
    image: 'realestate.png',
    url: 'https://realestate-mp0n.onrender.com',
    features: ['Real Estate Listings', '3D View', 'Map View', 'Inquiry via Email', 'Authentication']
  },
  {
    title: 'School Management System',
    image: 'school-manage.png',
    url: 'https://onqode-school.onrender.com',
    features: ['Django Backend', '2FA', 'CSV Imports', 'Notifications', 'Invoices/Receipts']
  },
  {
    title: 'Scribe Kit AI',
    image: 'scribekitai.jpg',
    url: 'https://scribekitai.netlify.app',
    features: ['20+ AI Tools', 'Wallet', 'Passwordless Login', 'Document Generation', 'Exams & Games']
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
    title: 'Ecommerce PWA',
    image: 'ecommerce.png',
    url: 'https://onqode-store.netlify.app',
    features: ['Product Search', 'Cart', 'Order and Pay', 'Admin Dashboard']
  },
  {
    title: 'VTU App (Web & Mobile)',
    image: 'vtu.jpg',
    url: 'https://mobiledata.onrender.com',
    features: ['Airtime & Data Purchase', 'Wallet', 'Email Receipts', 'PDF Downloads']
  },
  
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
    title: 'Flight Booking PWA',
    image: 'flight.png',
    url: 'https://onqode-booking.netlify.app',
    features: ['JWT Auth', 'Push Notifications', 'PDF Ticket', 'Admin Email Broadcast']
  }
]);

const techIcons = ref([
  { name: 'HTML', src: '/icons/html.svg' },
  { name: 'CSS', src: '/icons/css.svg' },
  { name: 'JavaScript', src: '/icons/javascript.svg' },
  { name: 'TypeScript', src: '/icons/typescript.svg' },
  { name: 'React', src: '/icons/react.svg' },
  { name: 'Vue', src: '/icons/vue.svg' },
  { name: 'Node.js', src: '/icons/nodejs.svg' },
  { name: 'Next.js', src: '/icons/nextjs.svg' },
  { name: 'Express.js', src: '/icons/express.svg' },
  { name: 'Django', src: '/icons/django.svg' },
  { name: 'Flutter', src: '/icons/flutter.svg' },
  { name: 'Supabase', src: '/icons/supabase.svg' },
  { name: 'Git', src: '/icons/git.svg' },
  { name: 'Java', src: '/icons/java.svg' },
]);

const floatingIcons = ref([
  { id: 1, name: 'code', style: 'position: absolute; top: 20px; left: 10%; transform: rotate(10deg); animation: float 6s ease-in-out infinite;' },
  { id: 2, name: 'storage', style: 'position: absolute; top: 60px; right: 10%; transform: rotate(-10deg); animation: float 5s ease-in-out infinite;' },
  { id: 3, name: 'developer_mode', style: 'position: absolute; bottom: 10px; left: 20%; transform: rotate(8deg); animation: float 7s ease-in-out infinite;' }
]);

  
const showProjectDetails = ref(false);
const projectDetailContent=ref([])


const filter=ref('')


const thumbStyle={
  opacity:'0',
  }
    

function scrollToTarget(id) {
  const target = document.getElementById(id);
  if (target) target.scrollIntoView({ behavior: 'smooth' });
}

function handleProjectDetails(details:any){
  projectDetailContent.value=details
  showProjectDetails.value=!showProjectDetails.value;
}
</script>

<style scoped>
/* Modern Portfolio Landing Page CSS */

/* Root Variables for Consistent Theming */
:root {
  --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  --secondary-gradient: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  --accent-gradient: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
  --dark-gradient: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
  --glass-bg: rgba(255, 255, 255, 0.1);
  --glass-border: rgba(255, 255, 255, 0.2);
  --shadow-light: 0 8px 32px rgba(31, 38, 135, 0.37);
  --shadow-heavy: 0 15px 35px rgba(0, 0, 0, 0.1);
  --animation-speed: 0.3s;
  --border-radius: 16px;
}

/* Global Styles */
* {
  box-sizing: border-box;
}

body {
  font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  overflow-x: hidden;
  scroll-behavior: smooth;
}

/* Animated Background */
#home {
  position: relative;
  overflow: hidden;
}

#home::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 20% 50%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
    radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.3) 0%, transparent 50%),
    radial-gradient(circle at 40% 80%, rgba(120, 219, 255, 0.3) 0%, transparent 50%);
  animation: backgroundMove 20s ease-in-out infinite;
  z-index: 1;
}

@keyframes backgroundMove {
  0%, 100% { transform: translateX(0) translateY(0); }
  25% { transform: translateX(-20px) translateY(-10px); }
  50% { transform: translateX(20px) translateY(10px); }
  75% { transform: translateX(-10px) translateY(20px); }
}

/* Enhanced Hero Section */
.bg-primary {
  background: var(--primary-gradient) !important;
  position: relative;
  z-index: 2;
}

/* Glassmorphism Cards */
.my-card {
  background: var(--glass-bg);
  backdrop-filter: blur(10px);
  border: 1px solid var(--glass-border);
  border-radius: var(--border-radius);
  box-shadow: var(--shadow-light);
  transition: all var(--animation-speed) ease;
  transform: translateY(0);
}

.my-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-heavy);
  background: rgba(255, 255, 255, 0.15);
}

/* Profile Image with Advanced Styling */
.q-img {
  transition: all var(--animation-speed) ease;
  position: relative;
  overflow: hidden;
}

.q-img:hover {
  transform: scale(1.05);
}

.q-img::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
  transform: translateX(-100%);
  transition: transform 0.6s ease;
  z-index: 1;
}

.q-img:hover::before {
  transform: translateX(100%);
}

/* Enhanced Buttons */
.q-btn {
  border-radius: 50px;
  padding: 12px 30px;
  font-weight: 600;
  text-transform: none;
  transition: all var(--animation-speed) ease;
  position: relative;
  overflow: hidden;
}

.q-btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s ease;
}

.q-btn:hover::before {
  left: 100%;
}

.q-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
}

/* Enhanced Typography */
.text-h5, .text-h6 {
  font-weight: 700;
  background: linear-gradient(45deg, #667eea, #764ba2);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.text-accent {
  color: #f5576c !important;
  text-shadow: 0 2px 8px rgba(245, 87, 108, 0.3);
}

/* Skills Section Enhancement */
.q-list .q-item {
  padding: 16px;
  border-radius: 12px;
  margin-bottom: 8px;
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(5px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all var(--animation-speed) ease;
}

.q-list .q-item:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateX(10px);
}

/* Tech Icons Animation */
.q-card[style*="width:80px"] {
  transition: all var(--animation-speed) ease;
  border-radius: 20px;
  background: var(--glass-bg);
  backdrop-filter: blur(10px);
  border: 1px solid var(--glass-border);
}

.q-card[style*="width:80px"]:hover {
  transform: scale(1.1) rotate(5deg);
  box-shadow: var(--shadow-light);
}

/* Project Cards Enhancement */
.q-card[style*="height:min-content"] {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

.q-card[style*="height:min-content"]:hover {
  transform: translateY(-15px) scale(1.02);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.q-card[style*="height:min-content"]::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: var(--accent-gradient);
  transform: scaleX(0);
  transition: transform 0.4s ease;
}

.q-card[style*="height:min-content"]:hover::before {
  transform: scaleX(1);
}

/* Dialog Enhancements */
.q-dialog .q-card {
  border-radius: 24px;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.25);
}

/* Scroll Area Styling */
.q-scroll-area {
  border-radius: 16px;
}

/* Contact Icons */
.q-icon {
  transition: all var(--animation-speed) ease;
}

.q-icon:hover {
  transform: scale(1.2);
  filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.2));
}

/* Social Links */
a {
  transition: all var(--animation-speed) ease;
  display: inline-block;
}

a:hover {
  transform: translateY(-3px);
}

/* Table Enhancements */
.q-table {
  background: transparent;
  border-radius: 16px;
  overflow: hidden;
}

.q-table .q-table__grid-content {
  gap: 24px;
}

/* Loading and Spinner Enhancements */
.q-spinner {
  filter: drop-shadow(0 0 10px rgba(102, 126, 234, 0.5));
}

/* Responsive Enhancements */
@media (max-width: 768px) {
  .my-card {
    margin: 16px 8px;
  }
  
  .q-btn {
    padding: 10px 20px;
    font-size: 14px;
  }
  
  .text-h5 {
    font-size: 1.8rem;
  }
  
  .text-h6 {
    font-size: 1.4rem;
  }
}

/* Additional Animations */
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}

@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
}

.animate__pulse {
  animation: pulse 3s ease-in-out infinite;
}

/* Floating Animation for Tech Icons */
.animate__zoomIn {
  animation: float 6s ease-in-out infinite;
}

.animate__zoomIn:nth-child(even) {
  animation-delay: -3s;
}

/* Enhanced Hover Effects */
.q-item-section:hover {
  color: #667eea;
  transition: color var(--animation-speed) ease;
}

/* Custom Scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb {
  background: var(--primary-gradient);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: var(--secondary-gradient);
}

/* Focus States */
.q-btn:focus,
.q-item:focus {
  outline: 2px solid #667eea;
  outline-offset: 2px;
}

/* Text Selection */
::selection {
  background: rgba(102, 126, 234, 0.3);
  color: white;
}

/* Loading States */
.q-img[src*="spinner"] {
  filter: blur(2px);
  transition: filter 0.3s ease;
}

.q-img[src*="spinner"]:hover {
  filter: blur(0);
}

/* Enhanced Section Spacing */
.q-mt-xl {
  margin-top: 80px !important;
}

.q-pa-md {
  padding: 24px !important;
}

/* Contact Section Enhancement */
#contact {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 32px 32px 0 0;
  margin-top: 80px;
  position: relative;
  overflow: hidden;
}

#contact::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 100" fill="rgba(255,255,255,0.1)"><polygon points="0,0 1000,100 1000,0"/></svg>');
  background-size: cover;
  z-index: 1;
}

#contact > * {
  position: relative;
  z-index: 2;
}

/* Performance Optimizations */
.q-card,
.q-btn,
.q-img {
  will-change: transform;
}

/* Print Styles */
@media print {
  .q-btn,
  .animate__animated,
  .q-dialog {
    display: none !important;
  }
  
  .my-card {
    box-shadow: none;
    border: 1px solid #ccc;
  }
}
</style>
  
