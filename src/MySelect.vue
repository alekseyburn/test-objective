<template>
    <div>
      <label>
        <select>
          <option v-for="item in source">{{ item.value }}</option>
        </select>
      </label>

      <p>Selected Value: {{value}}</p>
    </div>
</template>

<script>
  export default {
    props: {
      source: '',
    },
    data() {
      return {

      }
    }
  }
</script>

<style scoped>

</style>
