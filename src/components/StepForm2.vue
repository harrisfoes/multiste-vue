<script setup lang="ts">
import { ref } from 'vue';
const selectedPlan = ref<string>('')
import icon_arcade from '../assets/images/icon-arcade.svg'
import icon_advanced from '../assets/images/icon-advanced.svg'
import icon_pro from '../assets/images/icon-pro.svg'
import PlanOptions from './PlanOptions.vue';
</script>

<template>
  <h2>Select your plan</h2>
  <p>You have the option of monthly or yearly billing.</p>
  <div class="plan-container">
    <PlanOptions :image="icon_arcade" planLabel="Arcade" pricing="$9/mo" />
    <PlanOptions :image="icon_advanced" planLabel="Advanced" pricing="$12/mo" />
    <PlanOptions :image="icon_pro" planLabel="Pro" pricing="$15/mo" />
  </div>
  <input type="radio" id="arcade" value="Arcade" v-model="selectedPlan" />
  <label for="arcade">Arcade</label>
  <input type="radio" id="advanced" value="Advanced" v-model="selectedPlan" />
  <label for="advanced">Advanced</label>
  <input type="radio" id="Pro" value="Pro" v-model="selectedPlan" />
  <label for="pro">Pro</label>

  <div class="pill-box">
    <div>
      Monthly
    </div>
    <div class="toggle-switch">
      <input type="checkbox" id="toggle" class="toggle-checkbox">
      <label for="toggle" class="toggle-label">
        <span class="toggle-inner"></span>
        <span class="toggle-slider"></span>
      </label>
    </div>
    <div>
      Yearly
    </div>
  </div>

</template>

<style scoped>
.pill-box {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  background-color: #d6d9e6;
  border-radius: 4px;
  margin: 2rem 0;
  padding: 1.5rem 0.75rem;
}

/* Hide the default checkbox */
.toggle-checkbox {
  display: none;
}

/* Style the label as the track of the switch */
.toggle-label {
  display: block;
  overflow: hidden;
  cursor: pointer;
  border: 2px solid #ccc;
  /* Border for the track */
  border-radius: 999em;
  /* Creates the pill shape */
  height: 20px;
  /* Adjust height as needed */
  width: 42px;
  /* Adjust width as needed */
  position: relative;
  background-color: var(--denim);
  /* Off state background */
  transition: background-color 0.3s ease;
}

/* Style the inner part (optional, for text or color change) */
.toggle-inner {
  display: block;
  width: 200%;
  /* Allows for sliding effect */
  margin-left: -100%;
  transition: margin-left 0.3s ease;
}

/* Style the slider (the moving part) */
.toggle-slider {
  display: block;
  width: 50%;
  /* Half the width of the inner for the slider */
  height: 100%;
  background-color: #fff;
  /* Slider color */
  border-radius: 999em;
  position: absolute;
  top: 0;
  left: 0;
  box-shadow: 0 0 2px rgba(0, 0, 0, 0.3);
  transition: left 0.3s ease;
}

/* When the checkbox is checked (On state) */
.toggle-checkbox:checked+.toggle-label {
  background-color: var(--denim);
  /* On state background */
}

.toggle-checkbox:checked+.toggle-label .toggle-inner {
  margin-left: 0;
  /* Slides the inner part */
}

.toggle-checkbox:checked+.toggle-label .toggle-slider {
  left: 50%;
  /* Moves the slider to the right */
}
</style>
