<template>
  <div class="flex-score-hank">
    <slot name="content">

    </slot>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Flex',
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
.flex-score-hank{
  display: flex;
  gap:89px;
}
</style>
