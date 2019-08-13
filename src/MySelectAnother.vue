<template>
  <div>
    <div class="select">
      <label class="select__search search">
        <input class="search__input" v-model.trim="gender" type="text" placeholder="Выберите значение">
      </label>

      <label class="select__radio radio" v-for="item in filtered">
        <input class="radio__control visually-hidden" type="radio" name="chosen value" :key="item.key"
               :value="item.value" v-model="gender">
        <span class="radio__btn">{{item.value}}</span>
      </label>
    </div>

    <p>Выбранное значение: {{gender}}</p>
  </div>
</template>

<script>
  export default {
    props: [
      'source',
    ],
    data () {
      return {
        gender: '',
      }
    },
    computed: {
      filtered: function () {
        let that = this
        return this.source.filter(function (item) {
          return item.value.toLowerCase().indexOf(that.gender.toLowerCase()) !== -1
        })
      },
    },
  }
</script>

<style scoped>
  .select {
    position: relative;
    overflow-y: scroll;
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    width: 300px;
    box-shadow: 0 1px 8px 0 rgba(0, 0, 0, 0.75);
    max-height: 300px;
  }

  .search {
    position: sticky;
    top: 0;
    width: auto;
    display: flex;
  }

  .search__input {
    display: flex;
    width: 100%;
    margin: 0;
    padding: 15px;
    border: none;
    font-size: 20px;
    line-height: 1.2em;
    color: white;
    background-color: rgb(48, 175, 225);
  }

  .search__input::placeholder {
    color: white;
  }

  .radio {
    border-bottom: 1px solid #bdc0c1;
  }

  .radio__btn {
    display: block;
    font-size: 16px;
    line-height: 1.2em;
    padding: 8px 15px;
  }

  .radio:last-child {
    border-bottom: none;
  }

  .radio__control:hover + .radio__btn,
  .radio__control:focus + .radio__btn {
    box-shadow: 0 0 10px rgba(0, 0, 0, .1) inset;
  }

  .radio__control:checked + .radio__btn {
    background-color: #37e1f5;
  }

  .visually-hidden {
    position: absolute;

    width: 1px;
    height: 1px;
    margin: -1px;
    padding: 0;
    overflow: hidden;

    white-space: nowrap;

    border: 0;

    clip-path: inset(100%);
  }

  ::-webkit-scrollbar {
    width: 7px;
    border-radius: 5px;
  }

  ::-webkit-scrollbar-track {
    background: rgba(128, 130, 131, 0.25);
  }

  ::-webkit-scrollbar-thumb {
    background-color: rgb(81, 234, 255);
    border-radius: 5px;
  }

  ::-webkit-scrollbar-button {
    opacity: 0;
    display: none;
  }

</style>
