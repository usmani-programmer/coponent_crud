<template>
  <div class="row justify-center">
    <div class="col-8">
      <div> Edit Component My component</div>
      <q-form class="q-gutter-md" @submit="$emit('update',test)">
        <q-input
          filled
          v-model="test.name"
          label="Your name *"
          hint="Name and surname"
          lazy-rules
          :rules="[ val => val && val.length > 0 || 'Please type something']"
        />
        <div>
          <q-btn label="Update" type="submit" color="primary"/>
        </div>
      </q-form>
    </div>

  </div>
</template>

<script>
export default {
  // name: 'ComponentName',
  props:['test'],
  data () {
    return {}
  }
}
</script>
