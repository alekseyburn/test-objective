<template>
  <div id="app">

    <my-select
      :source="source"
      key-field="key"
      value-field="value"
    ></my-select>

    <hr>

    <my-select-another
      :source="source"
      v-model="gender"
    ></my-select-another>
  </div>

</template>

<script>
  import MySelect from './MySelect.vue'
  import MySelectAnother from './MySelectAnother.vue'

  export default {
    name: 'app',
    props: {
    },
    data () {
      return {
        source: [{key: 'm', value: 'male'}, {key: 'f', value: 'female'}],
        key: undefined,
        value: undefined,
        gender:''
      }
    },
    components: {
      mySelect: MySelect,
      mySelectAnother: MySelectAnother
    },
  }
</script>

<style>

</style>
