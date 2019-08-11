<template>
  <div id="app">

    <my-select></my-select>
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
    mySelect: MySelect
  }
}
</script>

<style>

</style>
