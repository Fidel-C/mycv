<!-- eslint-disable @typescript-eslint/no-unused-vars -->
<template>
<q-page  id="home">
    <div class="column bg-primary q-pa-md full-screen" style="min-height:60vh;">


<div class="row justify-center full-screen">

  <div class="column col-12 col-md-8 justify-center">
<div class="text-grey q-mt-xl text-h5 text-center">Hi</div>
<div data-aos="fade-right" data-aos-duration="1000" class="text-accent text-h5 q-my-lg text-center" id="about">I am Fidel C.</div>
    <!-- <q-img :src="'/profile.png'" spinner-color="accent" style="height: 150px; max-width: 150px;border-radius: 50%;" /> -->

<div data-aos="fade-left" data-aos-duration="1000" class="text-accent text-h6 text-center">A Full-stack Software Developer</div>

<div class="row q-my-md text-center justify-center full-screen">
  <q-btn v-if="!showDetails" color="secondary" flat icon="more" label="Read More About Me" @click="showDetails=true" />
<q-btn v-if="showDetails" color="secondary" flat icon="password" label="Hide Details" @click="showDetails=false" />

</div>
<div class="column col-md-8 col-12 items-center q-pa-md q-mb-md text-bold text-center full-width" v-if="showDetails">



<q-dialog v-model="showDetails">
  <q-card class="bg-primary text-accent q-pa-md full-width">
  <q-scroll-area style="height:70vh;">
 <div class="text-accent q-pa-md q-mx-auto">
  <span class="text-body2 text-italic q-my-md">
I  bring about a blend of legal expertise and a fervent passion for coding and technology. With a strong background in law and an insatiable penchant for all things tech-related, I have established a reputation for crafting innovative and efficient software solutions.

  </span>
  </div>
<div class="column text-accent text-center text-h6">
  Background, Education and Career
 <span class="text-body2 text-italic q-my-md">Born with a natural gift for problem-solving, I've always possessed a keen interest in both law and technology. Having obtained a degree in Law(LLB), and a BL,  I am now proceeding with a career as a lawyer, specialising in areas where technology and the legal world intersect, such as intellectual property, cybersecurity, etc.
 </span> </div>

<div class="column text-accent text-center text-h6">
       The Path <span class="text-body2 text-italic q-my-md"> Though without a degree in Computer Science or Engineering , I have found myself drawn to the rapidly evolving world of technology. I began exploring coding and software development as a hobby, dedicating my evenings and weekends to learn programming languages and experimenting with various projects. The more I delved into coding, the more I wanted to.
 </span>
</div>


<div class="column text-accent text-center text-h6">
Professional Expertise

<span class="text-body2 text-italic q-my-md">
As a full-stack software developer, I thrive on tackling challenging projects that require a comprehensive understanding of both front-end and back-end development. I excel in designing intuitive user interfaces, crafting scalable backend architectures, and ensuring seamless integration of the various components. My legal expertise allows me to comprehend the legal implications of software solutions, ensuring compliance with regulations and privacy standards.

</span>
</div>


<div class="column text-accent text-center text-h6">
Learning Philosophy
<span class="text-body2 text-italic q-my-md">
  I am a firm believer in lifelong learning and as such, I continuously keep up with the latest trends and advancements in technology. This is realisable by attending tech conferences, participating in hackathons, and contributing to open-source projects, while staying updated with the ever-changing landscape of software development.

</span>
</div>


<div class="column text-accent text-center text-h6">
Personal Projects and Hobbies

<span class="text-body2 text-italic q-my-md">
Outside of the professional sphere, I enjoy working on personal coding projects that address various social and environmental challenges. The idea is to develop applications that promote sustainability, advocate for legal-aid, e-commerce, finetch, and foster learning opportunities in underserved communities. My hobbies are coding, football, gaming, movies, music, etc.

</span>

</div>
<div class="column text-accent text-center text-h6">
<span class="text-body2 text-italic q-my-md">
I am a multifaceted individual whose journey in the legal world and full-stack software development exemplifies the power of passion and determination. My ability to combine legal expertise with coding skills has made me a valued asset in the tech industry. With an unwavering enthusiasm for technology, I will hopefully continue to make meaningful contributions to the world of software development, enriching the lives of many through innovative, user-friendly applications.

</span>

</div>
</q-scroll-area>

  <q-card-actions align="right">
        <q-btn flat label="close" color="secondary" v-close-popup />
      </q-card-actions>
  </q-card>
</q-dialog>
</div>



  </div>
   <div class="column col-md-4 col-12  q-pa-md justify-center items-center">

    <q-img :src="'/profile.png'" spinner-color="accent" style="height: 150px; max-width: 150px;border-radius: 50%;border-top:5px dotted #F2F4F7;border-bottom:3px dotted #F2F4F7;border-left:2px dotted #E43A19;" />

</div>

</div>





  <div class="row justify-around text-center">

    <div class="text-bold text-accent column">Email: <span class="text-grey">fidelchukwunyere@gmail.com</span></div>

    <div class="text-bold text-accent column">Linkedin: <span class="text-grey">Fidel Chukwunyere</span></div>
 <q-btn color="secondary" text-color="accent" label="Hire Me" @click="scrollToTarget('contact')"/>

  </div>



 </div>





<!-- end of blue or primary background -->
<div class="text-primary text-h5 text-center q-mt-xl text-underline text-bold">My Tech Skills?</div>


<div class="row q-gutter-md q-mt-xl q-pa-md justify-evenly items-center animate__animated animate__pulse animate__slower animate__infinite">

     <q-card class="my-card  justify-center q-pa-md  text-center" flat>

    <q-card-section horizontal class="q-mx-auto" >
<div class="q-mr-md">
  <q-icon name="fa fa-circle-check" class="text-primary" size="sm" />

 </div>

     <div class="text-primary ">
   Frontend
     </div>


     <div class="q-mr-md">
     <q-icon name="fa fa-chevron-right" class="text-primary text-bold" size="sm" />
</div>
    </q-card-section>

  </q-card>



   <q-card class="my-card  q-pa-md" flat>

    <q-card-section horizontal class="q-mx-auto">
<div class="q-mr-md">
     <q-icon name="fa fa-circle-check" class="text-secondary text-bold" size="sm" />
</div>

     <div class="text-primary">
   Backend
     </div>

      <div class="q-mr-md">
     <q-icon name="fa fa-chevron-right" class="text-primary text-bold" size="sm" />
</div>
    </q-card-section>



  </q-card>








     <q-card class="my-card  q-pa-md" flat>

    <q-card-section horizontal class="q-mx-auto" >
<div class="q-mr-md">
     <q-icon name="fa fa-circle-check" class="text-primary text-bold" size="sm" />
</div>
     <div class="text-primary">
   Mobile Apps
     </div>


     <div class="q-mr-md">
     <q-icon name="fa fa-chevron-right" class="text-primary text-bold" size="sm" />
</div>
    </q-card-section>

  </q-card>


  <q-card class="my-card  q-pa-md" flat>

<q-card-section horizontal class="q-mx-auto" >
<div class="q-mr-md">
 <q-icon name="fa fa-circle-check" class="text-secondary text-bold" size="sm" />
</div>
 <div class="text-primary">
Desktop Apps
 </div>


 <div class="q-mr-md">
 <q-icon name="fa fa-chevron-right" class="text-primary text-bold" size="sm" />
</div>
</q-card-section>

</q-card>

</div>



<div class="row q-mt-xl q-pa-md justify-center">


  <div class="column col-6 q-my-lg" style="max-height:750px;">



  <div class="q-mt-lg " style="border-radius:50%;">

    <q-list class="text-left">
      <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>HTML</q-item-section>
      </q-item>

        <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>CSS</q-item-section>
      </q-item>


        <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>Javascript</q-item-section>

      </q-item>

        <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>TypeScript</q-item-section>
      </q-item>

        <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>Python</q-item-section>
      </q-item>

        <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>Dart</q-item-section>
      </q-item>

        <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>Php</q-item-section>
      </q-item>

        <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>Git</q-item-section>
      </q-item>

        <q-item  >
        <q-item-section avatar>
          <q-icon color="primary" name="star" />
        </q-item-section>
        <q-item-section>Supabase</q-item-section>
      </q-item>
    </q-list>
  </div>

  </div>




   <div class="row col-6 q-my-lg q-gutter-sm items-center content-center animate__animated animate__zoomIn animate__slower "  style="max-height:750px;">

      <q-card class="" flat style="width:80px;height:80px;">

   <div class="q-pa-md q-ma-md">
        <q-icon name="css" size="lg" class="text-primary" />

          </div>
</q-card>


<q-card flat style="width:80px;height:80px;">

     <div class="q-pa-md q-ma-md">
<q-icon name="html" size="lg" class="text-primary" />

          </div>
</q-card>

<q-card flat style="width:80px;height:80px;">

     <div class="q-pa-md q-ma-md">
<q-icon name="php" size="lg" class="text-primary" />

          </div>
</q-card>

<q-card flat style="width:80px;height:80px;">

     <div class="q-pa-md q-ma-md">
      <q-img
        :src="'icons/vue.svg'"
        spinner-color="primary"
        spinner-size="82px"
      />

          </div>
</q-card>

<q-card flat style="width:80px;height:80px;">

     <div class="q-pa-md q-ma-md">
      <q-img
        :src="'/icons/laravel.svg'"

        spinner-color="primary"
        spinner-size="82px"
      />

          </div>
</q-card>

<q-card flat style="width:80px;height:80px;">

     <div class="q-pa-md q-ma-md">
      <q-img
        :src="'icons/javascript.svg'"

        spinner-color="primary"
        spinner-size="82px"
      />

          </div>
</q-card>

<q-card flat style="width:80px;height:80px;">

     <div class="q-pa-md q-ma-md">
      <q-img
        :src="'/icons/django.svg'"

        spinner-color="primary"
        spinner-size="82px"
      />

          </div>
</q-card>

<q-card flat style="width:80px;height:80px;">

       <div class="q-pa-md q-ma-md">
      <q-img
        :src="'/icons/python1.svg'"
        spinner-color="primary"
        spinner-size="82px"
      />

          </div>
</q-card>

<q-card flat style="width:80px;height:80px;">

     <div class="q-pa-md q-ma-md">
      <q-img
        :src="'/icons/flutter.svg'"
        spinner-color="primary"
        spinner-size="82px"
      />

          </div>
</q-card>





  </div>






</div>






<div   class="row bg-primary q-pa-md q-mx-auto items-center justify-between text-center" style="height:50vh;">

  <q-btn flat label="Experience"  icon="fa fa-calendar" class="text-accent " size="lg" />
  <q-btn data-aos="flip-left"  data-aos-duration="1000"  flat label="Awards"  icon="fa fa-award" class="text-accent " size="lg"  />
  <q-btn flat label="Projects" @click="scrollToTarget('projects')"  icon="settings" class="text-accent " size="lg"  />
  <q-btn data-aos="flip-up"  data-aos-duration="1000"  flat label="Clients"  icon="group" class="text-accent " size="lg"  />

</div>



<div id="projects" class="column q-mt-xl q-pa-md q-ma-auto">

  <div class="text-center text-h5 text-bold text-primary">Some of My Projects</div>

  <q-table
   title=""
  :rows="rows"
  :filter="filter"
  :rows-per-page-options="[12, 15, 20]"
  :rows-per-page="10"
  grid
>






<template #item="project">
       <q-card data-aos="slide-up"  data-aos-duration="1000"   class="my-card q-ma-md q-my-xl q-mx-auto"  style="height:min-content;width:300px;border-radius:30px;box-shadow: 5px 5px #111F4D;">
    <q-img
    :src="project.row.image"
    :ratio="16/9"
    spinner-color="primary"
    spinner-size="82px"
    style="width:100%;height:auto;border-top-right-radius:30px;border-top-left-radius:30px;"
   >
   <div class="absolute-bottom text-bold text-subtitle1  text-center">
       {{project.row.title}}
     </div>


  </q-img>



 <q-card-section horizontal class="row q-pa-sm justify-between items-center">






 </q-card-section>


 <q-card-actions class="row q-mt-auto">
    <q-btn   no-caps flat  label="View Details" class="text-primary text-center q-mx-auto" @click="handleProjectDetails(project.row)"  />
 </q-card-actions>
  </q-card>


</template>





</q-table>

</div>





<div class="column q-pb-xl q-mt-xl" id="contact">

  <div class="text-center text-bold text-h5">Contact Me</div>

  <div class="row q-pa-md justify-evenly animate__animated animate__pulse animate__slower animate__infinite">

  <a href="mailto:fidelchukwunyere@gmail.com"  target="_blank" class="has-text-light" ><b-image src="/email.png" class="socials"> </b-image>
   <q-icon name="mdi-gmail" size="lg" class="text-red" />
  </a>

  <a href="https://wa.me/+2347064620806" target="_blank" class="has-text-light "
            >

            <q-icon name="mdi-whatsapp" class="text-green" size="lg" />
          </a>


              <a href="https://m.me/febuka1" target="_blank"  class="has-text-light"
            >
            <q-icon name="facebook" size="lg" />
          </a>

  </div>
</div>













<q-dialog v-model="showProjectDetails">
  <q-card>
   <div class="q-mx-auto">
    <q-img
      :src="projectDetailContent.image"
      :ratio="16/9"
      spinner-color="primary"
      spinner-size="82px"
    />
   </div>
    <div class="text-h6 text-center">{{projectDetailContent.title}}</div>

    <q-card-section class="row items-center">
      <q-list bordered>
      <q-item v-for="i in projectDetailContent.features" :key="i" >
        <q-item-section avatar>
          <q-icon color="secondary" name="star" />
        </q-item-section>
        <q-item-section>{{i}}</q-item-section>
      </q-item>
    </q-list>
    </q-card-section>
    <q-card-actions align="right">
      <q-btn flat label="Close" no-caps color="primary" v-close-popup />

      <a v-if="projectDetailContent.url!=''" :href="projectDetailContent.url" target="_blank" >
<q-btn  color="primary"  icon="fa fa-eye" label="View Demo" flat v-close-popup />
</a>
    </q-card-actions>
  </q-card>
</q-dialog>



</q-page>
</template>

<script setup lang="ts">
import { ref} from 'vue'
import 'animate.css'





const columns = ref([
  { field: 'title', name: 'title', label: 'Project',align:'left' },
   { field: 'features', name: 'features', label: 'Features',align:'left' },
  { field: 'url', name: 'url', label: 'Demo',align:'left' },


]);

const rows = ref([

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
    title: 'Flight Booking PWA',
    url: 'https://onqode-booking.netlify.app',
    image:'flight.png',
    features: [
      'FastApi Backend',
      'JWT Authentication',
      'Sign-up Email verification',
      'Realtime Push Notifications by admin',
      'User can manage booking from user dashboard',
      'User can download flight assTicket as PDF',
      'User can optionally mark notification as read',
      'Admin can send special email to user or a mass mail to all users',
    ],
  },
]);

const showDetails = ref(false);
const showProjectDetails = ref(false);
const projectDetailContent=ref([])


const filter=ref('')


const thumbStyle={
  opacity:'0',
}



function scrollToTarget(id: string) {
  const target = document.getElementById(id);
  if (target) {
    target.scrollIntoView({ behavior: 'smooth' });
  }
}


function handleProjectDetails(details:any){
  projectDetailContent.value=details
  showProjectDetails.value=!showProjectDetails.value;
}


</script>

<style scoped></style>
