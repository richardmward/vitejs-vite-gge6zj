<template>
  <div style="background: #ddd; padding: 4px">
    <h2>{{ title }}</h2>
    <div v-for="item in items" :key="item.id">
      <Starport :port="item.id" style="height: 130px">
        <SListItem v-bind="item" @click="$emit('toggle', item)" />
      </Starport>
    </div>
  </div>
</template>

<script>
import { Starport } from 'vue-starport';
import SListItem from './SListItem.vue';

export default {
  components: {
    Starport,
    SListItem,
  },
  props: {
    title: String,
    items: Array,
  },
};
</script>
