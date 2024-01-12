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
   @delete="del"
   @edit="editForm"
 />
  <edit_data
  v-if="display==='edit'"
  :test="edit_data.record"
  @update="update_data"
  />
</template>
<script>
import Add_data from "components/add_data.vue";
import View_data from "components/view_data.vue";
import Edit_data from "components/edit_data.vue";

export default {
  components: {Edit_data, View_data, Add_data},
  name: 'ParentPage',
  data(){
    return{
      display:'add_data',
      ay:[],
      edit_data: null,
    }
  },
  methods :{
    add(test){
      this.ay.push(test)
      // console.log(this.ay)
      this.display='view_data'
    },
    del(index){
      this.ay.splice(index,1)
    },
    editForm(data){
      this.edit_data=data;
      this.display='edit'
    },
    update_data(grade){
      this.ay[this.edit_data.index] = grade;
      this.display='view_data';
      this.edit_data = null;
    }
  }
}

</script>
