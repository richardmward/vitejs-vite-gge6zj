<template>
  <div
    style="background: #eee; border: 2px solid #aaa; padding: 4px; margin: 4px"
  >
    <h3>{{ title }}</h3>
    <p>{{ body }}</p>
    <p style="font-size: 0.75em">{{ id }}</p>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    body: String,
    id: String,
  },
};
</script>
