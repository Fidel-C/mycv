<template>
  <q-layout view="lHh Lpr lFf bg-accent">
    <q-header flat>
      <q-toolbar class="q-ml-auto">

        <q-toolbar-title class=" text-bold">
          Fidel C<q-img :src="'/profile.png'" spinner-color="accent" style="height:20px;width:20px;border-radius: 50%;border-top:3px dotted #F2F4F7;border-bottom:2px dotted #F2F4F7;border-left:2px dotted #E43A19;" />

        </q-toolbar-title>

        <div class="q-ml-auto q-my-auto">

          <q-icon  flat size="xs" name="mdi-brightness-5"  class="text-light"  />
          <q-icon v-if="isDark" flat size="md" name="mdi-toggle-switch"  class="text-light q-mt-md q-mx-md cursor-pointer" @click="toggleTheme" />


<q-icon v-if="!isDark" flat size="md" name="mdi-toggle-switch-off"  class="text-dark q-mt-md q-mx-md cursor-pointer" @click="toggleTheme" />
<q-icon  flat size="xs" name="mdi-brightness-2"  class="text-dark" />
</div>

         <div class="flex q-mx-md" v-if="$q.screen.width>=600">

           <q-btn flat color="white"  label="Home" @click="scrollToTarget('home')" />

           <q-btn flat color="white"  label="About" @click="scrollToTarget('about')" />

         <q-btn flat color="white"  label="Projects" @click="scrollToTarget('projects')" />
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
      class="text-white bg-primary"
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

    <!-- <q-footer flat bordered reveal  v-model="footer" class="bg-primary" v-if="$q.screen.width>=600">
      <div class="row justify-evenly items-center q-py-md content-center">
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

    </q-footer> -->
  </q-layout>
</template>

<script lang="ts" setup>
import { ref ,computed,watch} from 'vue';
import { LocalStorage, useQuasar } from 'quasar';
import EssentialLink from 'components/EssentialLink.vue';
import { setInterval } from 'timers';


const $q=useQuasar()
const footer=ref($q.appVisible)

const isDark=ref(JSON.parse(localStorage.getItem('isDark'))||false)


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
    icon: 'money',
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






function toggleTheme(){
$q.dark.toggle()
localStorage.setItem('isDark',JSON.stringify($q.dark.isActive))
isDark.value=$q.dark.isActive

}


function checkActiveTheme(){
 if(JSON.parse(localStorage.getItem('isDark'))==true){
  isDark.value==true
  $q.dark.set(true)
 }else{
  isDark.value=false
  $q.dark.set(false)

 }
}


checkActiveTheme()

</script>



<style>
body{
  overflow-x:hidden;
}

</style>
