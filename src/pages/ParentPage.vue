<template>
<!--  <q-page >-->
<!--    &lt;!&ndash; content &ndash;&gt;-->
<!--    <h5>its parent page</h5>-->
<!--  </q-page>-->
  <div class="text-center bg-teal-"><h5>Its Main Parent Page</h5></div>
  <div class="text-center q-mt-md q-pa-lg">
    <q-btn class="q-pa-md" color="green" label="Add-Data" @click="display='add_data' "/>
    <q-btn class="q-pa-md q-ml-md" color="blue" label="View-Data" @click="display='viwe_data' "/>
  </div>
  <add_data
    v-if="display==='add_data'"
    @submit ='add'
  />
 <view_data
   v-if="display==='view_data'"
   :my_array="ay"
 />
</template>
<script>
import Add_data from "components/add_data.vue";
import View_data from "components/view_data.vue";

export default {
  components: {View_data, Add_data},
  name: 'ParentPage',
  data(){
    return{
      display:'add_data',
      ay:[],
    }
  },
  methods :{
    add(test){
      this.ay.push(test)
      // console.log(this.ay)
      this.display='view_data'
    }
  }
}

</script>
