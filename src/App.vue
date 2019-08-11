<template>
  <div id="app">

    <my-select
      :source="[{key: 'm', value: 'male'}, {key: 'f', value: 'female'}]"
    ></my-select>
  </div>
</template>

<script>
  import MySelect from './MySelect.vue'

  export default {
    name: 'app',
    data () {
      return {

      }
    },
    components: {
      mySelect: MySelect,
    },
  }
</script>

<style>

</style>
