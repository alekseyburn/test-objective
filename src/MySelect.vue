<template>
  <div>
    <label>
      <input type="text" v-model.trim="gender">
      <select v-model="gender">
        <option v-for="item in filtered" :value="item.value" :key="item.key">{{ item.value }}</option>
      </select>
    </label>
    <p>Selected Gender: {{gender}}</p>
  </div>
</template>

<script>
  export default {
    props: [
      'source',
      'key-field',
      'value-field',
    ],
    data () {
      return {
        gender: '',
      }
    },
    computed: {
      filtered () {
        let that = this
        return this.source.filter(function (item) {
          return item.value.toLowerCase().indexOf(that.gender.toLowerCase()) !== -1
        })
      }
    }
  }
</script>

<style scoped>

</style>
