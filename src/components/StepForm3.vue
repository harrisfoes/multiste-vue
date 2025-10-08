<script setup lang="ts">
const addonData: ({
  id: string,
  name: string,
  subhead: string,
  price: string
})[] = [
    {
      id: "online-service",
      name: "Online Service",
      subhead: "Access to multiplayer games.",
      price: "+$1/mo",
    },
    {
      id: "larger-storage",
      name: "Larger storage",
      subhead: "Extra 1TB of cloud save",
      price: "+$2/mo",
    },
    {
      id: "customizable-profile",
      name: "Customizable provile",
      subhead: "Custom theme on your profile",
      price: "+2/mo",
    }
  ]
</script>

<template>
  <h2>Pick add-ons</h2>
  <p>Add-ons help enhance your gaming experience.</p>
  <div class="add-on-options" v-for="(addon, index) in addonData" :key="index">
    <input type="checkbox" :id="addon.id">
    <div class="addon-text-holder">
      <div class="addon-name">
        {{ addon.name }}
      </div>
      <div class="addon-subhead">{{ addon.subhead }}</div>
    </div>
    <div class="addon-price">{{ addon.price }}</div>
  </div>
</template>

<style scoped>
input[type="checkbox"] {
  width: 20px;
  height: 20px;
}

.addon-text-holder {
  flex-grow: 4;
  margin: 0 1rem;

}

.add-on-options {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  box-sizing: border-box;
  border: 1px solid var(--border-color);
  border-radius: 8px;
  padding: 1rem 1rem;
  margin: .75rem 0;
}

.addon-name {
  color: var(--denim);
  font-weight: semibold;
  line-height: 1.75rem;
}

.addon-price {
  color: var(--purple)
}
</style>
