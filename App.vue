<template>
  <div id="app">
    <ItemList />
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue';

export default {
  name: 'App',
  components: {
    ItemList,
  },
};
</script>

<style>
#app {
  font-family: cursive;
  text-align: center;
  color: #a5ffff;
  margin-top: 60px;
}
</style>