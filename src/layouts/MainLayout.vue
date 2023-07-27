<template>
  <q-layout view="lHh Lpr lFf bg-accent">
    <q-header flat class="bg-accent">
      <q-toolbar class="q-ml-auto">

        <q-toolbar-title class="text-primary text-bold">
          Fidel C<q-icon name="star" class="text-secondary q-my-auto" />
        </q-toolbar-title>



         <div class="flex q-mx-md" v-if="$q.screen.width>=600">

           <q-btn flat color="white" text-color="black" label="Home" @click="scrollToTarget('home')" />

           <q-btn flat color="white" text-color="black" label="About" @click="scrollToTarget('about')" />

         <q-btn flat color="white" text-color="black" label="Projects" @click="scrollToTarget('projects')" />
          <q-btn  outline  text-color="secondary" label="contact me" @click="scrollToTarget('contact')"  />

         </div>


         <q-btn
         v-if="$q.screen.width<600"
          class="text-secondary"
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
      </q-toolbar>



    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      v-if="$q.screen.width<600"
      :side="'right'"
      :breakpoint="100"
      class="bg-accent text-primary"
      bordered
      overlay
      >
      <q-list>
        <q-item-label
          header
        >
         Shortcuts
        </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          :caption="link.caption"
          :icon="link.icon"
          :link="link.link"
          :title="link.title"

          @link:clicked="scrollToTarget"


        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer flat bordered reveal  v-model="footer" class="bg-primary">
      <div class="row justify-around items-center q-py-md">
             <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          :caption="link.caption"
          :icon="link.icon"
          :link="link.link"
          :title="link.title"

          @link:clicked="scrollToTarget"


        />

      </div>

    </q-footer>
  </q-layout>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import { useQuasar } from 'quasar';
import EssentialLink from 'components/EssentialLink.vue';


const $q=useQuasar()
const footer=ref($q.appVisible)
const linksList = ref([



 {
    title: 'Home',
    caption: 'Home',
    icon: 'home',
    link: 'home'
  },  {
    title: 'About',
    caption: 'About',
    icon: 'help',
    link: 'about'
  },
  {
    title: 'Projects',
    caption: 'projects',
    icon: 'folder',
    link: 'projects'
  },
  {
    title: 'Contact',
    caption: 'contact',
    icon: 'phone',
    link: 'contact'
  },

  {
    title: 'Hire Me',
    caption: 'hire me',
    icon: 'dollar',
    link: 'contact'
  }
])
const leftDrawerOpen = ref(false)

function scrollToTarget(id: string) {
  const target = document.getElementById(id);
  if (target) {
  target.scrollIntoView({behavior:'smooth'})
  }
}


 function toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }




</script>


