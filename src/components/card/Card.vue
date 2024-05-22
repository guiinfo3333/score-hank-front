<script setup lang="ts">

defineProps<{
  msg: string
}>()
</script>

<template>
  <div class="card-score-hank">
      <slot name="content">

      </slot>
  </div>
</template>

<style scoped>
  .card-score-hank{
    padding-top: 30px;
    width: 100%;
    max-width: 513px;
    background: white;
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
    height: 170px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>