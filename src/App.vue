<template>
  <AddInput @data="displayItems" />
  <div v-for="item in itemsArray" :key="item">
    <h3>{{ item }}</h3>
  </div>
  <button @click="random">Random select</button>
  <Result v-if="itemSelected" :itemSelected="itemSelected" />
</template>

<script>
import AddInput from './components/AddInput.vue';
import Result from './components/Result.vue';

export default {
  name: 'App',
  components: {
    AddInput,
    Result,
  },
  data() {
    return {
      itemsArray: [],
      itemSelected: '',
    };
  },
  methods: {
    displayItems(items) {
      this.itemsArray = items;
    },
    random() {
      this.itemSelected =
        this.itemsArray[Math.floor(Math.random() * this.itemsArray.length)];
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
