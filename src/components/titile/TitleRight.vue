<template>
  <div>
    <h1>{{ message }}</h1>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Title',
  props: {
    message: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
h1 {
  font-family: 'Roboto', sans-serif;
  color: black;
  font-size: 1.2rem;
  font-weight: 400;
  padding-left: 28px;
  padding-top: 20px;
}
</style>
