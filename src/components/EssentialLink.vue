 <template>
  <q-item
   clickable
  @click="sendLink(link)"
  >
    <q-item-section
      v-if="icon"
       avatar
    >
      <q-icon :name="icon" />
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
      <q-item-label caption>{{ caption }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script lang="ts" setup>
import { toRefs } from 'vue';


const emit = defineEmits(['link:clicked'])

const props=defineProps({
    title: {
      type: String,
      required: true
    },
  icon: {
      type: String,
      required:true
    },
  caption: {
      type: String,
      required:true
    },
      link: {
      type: String,
      required:true
    },


  })

toRefs(props)


function sendLink(val:any) {
  emit('link:clicked',val)

}

</script>
