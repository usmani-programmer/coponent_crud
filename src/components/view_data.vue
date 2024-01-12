<template>
<div class="row justify-center">
  <div class="col-8">
    <div>My component</div>
    <q-markup-table>
      <thead>
      <tr>
        <th class="text-center">Name</th>
        <th class="text-center">Actions</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(item, index) in my_array">
        <td class="text-center">{{item.name}}</td>
        <td class="text-center">
          <q-btn color="green" label="edit" @click="$emit('edit',{record: item, index: index})" />
          <q-btn color="red" label="delete" class="q-ml-md" @click="$emit('delete',index)" />
        </td>
      </tr>
      </tbody>
    </q-markup-table>
  </div>
</div>

</template>

<script>
export default {
  // name: 'ComponentName',
  props:['my_array'],
  emits:['delete','edit'],
  data () {
    return {}
  }
}
</script>
