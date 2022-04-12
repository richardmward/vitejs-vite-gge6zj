<template>
  <div style="background: #ddd; padding: 4px">
    <h2>{{ title }}</h2>
    <div v-for="item in items" :key="item.id">
      <SListItem v-bind="item" @click="$emit('toggle', item)" />
    </div>
  </div>
</template>

<script>
import SListItem from './SListItem.vue';

export default {
  components: {
    SListItem,
  },
  props: {
    title: String,
    items: Array,
  },
};
</script>
