<template>
    <div>
      <label>
        <select v-model="gender">
          <option v-for="item in source">{{ item.value }}</option>
        </select>
      </label>
      <p>Selected Gender: {{gender}}</p>
    </div>
</template>

<script>
  export default {
    props: [
      'source',
    ],
    data() {
      return {
        gender: undefined
      }
    }
  }
</script>

<style scoped>

</style>
