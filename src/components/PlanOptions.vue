<script setup lang="ts">
const props = defineProps<{
  image: string,
  planLabel: string,
  pricing: string
}>()
</script>

<template>
  <div class="plan arcade">
    <img :src="props.image" />
    <div class="plan-text">
      <div class="plan-label">
        {{ props.planLabel }}
      </div>
      <div>
        {{ props.pricing }}
      </div>
    </div>
  </div>
</template>

<style lang="css" scoped>
.plan {
  width: 100%;
  padding: 1.25rem 1rem;
  box-sizing: border-box;
  border: solid 1px var(--light-grey);
  border-radius: 7.5px;
  display: flex;
  gap: .5rem;
  margin: .5rem 0;
}

.plan-text {
  display: flex;
  flex-direction: column;
  gap: .4rem;
}

.plan-label {
  color: var(--denim);
  font-size: 15px;
  font-weight: 499;
}
</style>
