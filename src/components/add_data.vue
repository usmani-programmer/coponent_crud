<template>
  <div class="q-pa-md row justify-center ">
    <div class=" col-md-4 ">
      <div class="">Add_data component</div>
      <div class="">
         <q-form class="q-gutter-md" @submit="$emit('submit',test)">
      <q-input
        filled
        v-model="test.name"
        label="Your name *"
        hint="Name and surname"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />
      <q-toggle v-model="accept" label="I accept the license and terms" />
      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
     </div>
   </div>
  </div>

</template>

<script>
export default {
  name: 'add_data',
  props:['test'],
  emits:['submit'],
  data () {
    return {
      test : {
        name:'',
      }
    }
  }
}
</script>
