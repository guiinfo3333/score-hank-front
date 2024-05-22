<template>
 <img :src="path" class="img-src">
</template>

<script lang="ts">
export default {
  name: 'Team',
  props: {
    name: {
      type: String,
      required: true,
    },
  },
  computed: {
    path() {
       return "/src/assets/escudos-time/" + this.name + ".png";
    }
  }
};
</script>

<style scoped>
h1 {
  font-family: 'Roboto', sans-serif;
  color: black;
  font-size: 1.5rem;
  font-weight: 400;
  padding-left: 44px;
  padding-top: 25px;
  padding-bottom: 26px;
}

.img-src{
  position: relative;
  width: 51px;
  height: 51px;
}
</style>
