<script setup lang="ts">
import { ref } from 'vue';
import bg_mobile from '@/assets/images/bg-sidebar-mobile.svg'
import StepItem from './components/StepItem.vue';
import StepForm2 from './components/StepForm2.vue';
import StepForm3 from './components/StepForm3.vue';

const currentStep = ref<number>(1)
currentStep.value = 1;

function nextStep() {
  if (currentStep.value < 4) {
    currentStep.value += 1;
  }
  console.log(currentStep.value);
}

function goBack() {
  if (currentStep.value !== 1) {
    currentStep.value -= 1;
  }
  console.log(currentStep.value);
}
</script>

<template>
  <div class="container">
    <main>
      <div class="bg-sidebar">
        <img :src="bg_mobile" class="bg-mobile" alt="mobile background">
      </div>
      <div class="step-counter">
        <StepItem v-for="n in 4" :key="n" :step-num="n" />
      </div>
      <div class="form-card" v-if="currentStep == 1">
        <h2>Personal info</h2>
        <p>
          Please provide your name, email address, and phone number.
        </p>
        <label>
          Name
        </label>
        <div>
          <input class="step-1" placeholder="e.g. Stephen King" />
        </div>
        <label>
          Email Address
        </label>
        <div>
          <input class="step-1" type="email" placeholder="e.g. stephenking@lorem.com" />
        </div>
        <label>
          Phone Number
        </label>
        <div>
          <input class="step-1" placeholder="e.g. 1 234 567 890" />
        </div>
      </div>
      <div class="form-card" v-if="currentStep == 2">
        <StepForm2 />
      </div>
      <div class="form-card" v-if="currentStep == 3">
        <StepForm3 />
      </div>
      <button v-if="currentStep !== 1" class="go-back" @click="goBack">Go Back</button>
      <button class="next-step" @click="nextStep">Next Step</button>
    </main>
    <footer>
    </footer>
  </div>
</template>

<style>
:root {
  --bg-color: #eff5ff;
  --border-color: #d6d9e6;
  --denim: #022959;
  --grey: #9699aa;
  --light-blue: #abbcff;
  --light-grey: #d6d9e6;
  --orange: #ffaf7e;
  --pink: #f9818e;
  --purple: #483eff;
  --red-errors: #ee374a;
  --sky-blue: #bee2fd;
  --vl-grey: #f8f9ff;
  --white: #ffffff;
}

body {
  background-color: var(--bg-color);
  font-family: Ubuntu, sans-serif;
  margin: 0 auto;
  color: var(--grey);
}

.container {
  position: relative;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.bg-mobile {
  width: 100%;
  position: absolute;
  z-index: -2;
}

.step-counter {
  display: flex;
  gap: 1rem;

  position: absolute;
  top: 48px;
  left: 50%;
  transform: translateX(-50%)
}

h2 {
  color: var(--denim);
  font-size: 24px;
}

p {
  font-size: 16px;
  line-height: 25px;
}

label {
  font-size: 12px;
  color: var(--denim);
}

.step-1 {
  border: 1px solid var(--border-color);
  height: 40px;
  width: 100%;
  box-sizing: border-box;
  margin: 0.25rem 0rem;
  padding: 0px 12px;
  border-radius: 4px;
}

.form-card {
  background-color: var(--white);
  border-radius: 10px;
  margin: 0rem 2rem;
  margin-top: 7.5rem;
  padding: 2rem 2rem;
  border: 1px solid var(--border-color);
  box-shadow: 0px 25px 40px -20px rgba(0, 0, 0, 0.1)
}

button {
  background: none;
  border: none;
  margin: 0;
  font: inherit;
  text-align: center;
  color: white;
}

.next-step {
  position: absolute;
  background-color: var(--denim);
  height: 40px;
  width: 97px;
  border-radius: 4px;
  inset: auto 32px 32px auto;
}

.go-back {
  position: absolute;
  color: var(--grey);
  height: 40px;
  width: 90px;
  border-radius: 4px;
  inset: auto 32px 32px 32px;
}

footer {
  background-color: var(--white);
  height: 6rem;
}
</style>
