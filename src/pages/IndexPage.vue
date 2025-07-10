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

function scrollToTarget(id) {
  const target = document.getElementById(id);
  if (target) target.scrollIntoView({ behavior: 'smooth' });
}

function handleProjectDetails(row) {
  alert(`You clicked on: ${row.title}`);
}
</script>

<style scoped>
.floating-icon {
  opacity: 0.2;
  z-index: 0;
}

@keyframes float {
  0% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(10deg); }
  100% { transform: translateY(0px) rotate(0deg); }
}
</style>
  
