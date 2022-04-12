<template>
  <div id="app">
    <h1>Starport lists</h1>
    <div style="display: flex; gap: 4px">
      <SList
        title="List 1"
        style="flex: 1"
        :items="list1Items"
        @toggle="toggle"
      />
      <SList
        title="List 2"
        style="flex: 1"
        :items="list2Items"
        @toggle="toggle"
      />
    </div>
    <StarportCarrier />
  </div>
</template>

<script>
import { StarportCarrier } from 'vue-starport';
import SList from './components/SList.vue';

export default {
  name: 'App',
  components: {
    StarportCarrier,
    SList,
  },
  data: () => ({
    items: [
      { id: '1', list: 'LIST1', title: 'Item 1', body: 'Item 1 body' },
      { id: '2', list: 'LIST1', title: 'Item 2', body: 'Item 2 body' },
      { id: '3', list: 'LIST1', title: 'Item 3', body: 'Item 3 body' },
      { id: '4', list: 'LIST1', title: 'Item 4', body: 'Item 4 body' },
    ],
  }),
  computed: {
    list1Items() {
      return this.items.filter((i) => i.list === 'LIST1');
    },
    list2Items() {
      return this.items.filter((i) => i.list === 'LIST2');
    },
  },
  methods: {
    toggle(item) {
      item.list = item.list === 'LIST1' ? 'LIST2' : 'LIST1';
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
