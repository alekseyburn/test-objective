<template>
  <div id="app">

    <my-select
      :source="source"
    ></my-select>

  </div>
</template>

<script>
  import MySelect from './MySelect.vue'

  export default {
    name: 'app',
    props: {
    },
    data () {
      return {
        source: [{key: 'm', value: 'male'}, {key: 'f', value: 'female'}],
      }
    },
    components: {
      mySelect: MySelect,
    },
  }
</script>

<style>

</style>
