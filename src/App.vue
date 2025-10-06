<script setup lang="ts"></script>

<template>
  <main>
    <div class="form-card">
      <h2>Personal info</h2>
      <p>
        Please provide your name, email address, and phone number.
      </p>
      <form>
        <label>
          Name
        </label>
        <div>
          <input placeholder="e.g. Stephen King" />
        </div>
        <label>
          Email Address
        </label>
        <div>
          <input type="email" placeholder="e.g. stephenking@lorem.com" />
        </div>
        <label>
          Phone Number
        </label>
        <div>
          <input placeholder="e.g. 1 234 567 890" />
        </div>
        <button>Next Step</button>
      </form>
    </div>
  </main>
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
}

h2 {
  color: var(--denim);
}

.form-card {
  background-color: var(--white);
  border-radius: 10px;
  margin: 2rem 2rem;
  padding: 2rem 2rem;
  border: 1px solid var(--border-color);
}
</style>
