<script setup lang="ts">
const props = defineProps<{ stepNum: number }>()
</script>

<template>
  <span class="steps">{{ props.stepNum }}</span>
</template>

<style scoped>
.steps {
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid var(--white);
  color: var(--white);
  font-weight: bold;
  height: 33px;
  width: 33px;
  border-radius: 50%;
}
</style>
