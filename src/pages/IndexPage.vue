<template>
  <q-page >
<div class="text-center q-mt-md q-pa-lg">
  <q-btn
  class="q-pa-md"
  color="green"
  label="Add-Data"
  />
</div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  data() {
    return {
      model: 'true',
    }
  },

  created() {
    console.log('after created')
  },
  beforeCreate() {
    console.log('before create hook running!')
  },

  beforeMount() {
    console.log('before mount hook running!')
  },

  beforeUnmount() {
    alert('are you sure you want to leave this page')
    console.log('mounted mount hook running!')
  },

})
</script>
