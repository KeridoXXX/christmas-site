<script></script>

<template>
  <div>
    <div class="welc">
      <h1>Julemanden er webudvikler!</h1>
      <h2>Og jeg har glemt at købe julegaver til...</h2>
    </div>
    <div>
      <ul>
        <li @click="selectedItem = 'mor-mai'">Mor Mai</li>
        <li @click="selectedItem = 'mor-sus'">Mor Sus</li>
        <li @click="selectedItem = 'hjalmar'">Hjalmar</li>
        <li @click="selectedItem = 'vilhelm'">Vilhelm</li>
        <li @click="selectedItem = 'mor-gitte'">Mor Gitte</li>
      </ul>
    </div>

    <!-- Render the selected component based on the selectedItem -->
    <div v-if="selectedItem === 'mor-mai'">
      <!-- Replace with your actual component -->
      <p>Content for Mor Mai</p>
    </div>
    <div v-if="selectedItem === 'mor-sus'">
      <!-- Replace with your actual component -->
      <p>Content for Mor Sus</p>
    </div>
    <div v-if="selectedItem === 'hjalmar'">
      <!-- Replace with your actual component -->
      <p>Content for Hjalmar</p>
    </div>
    <div v-if="selectedItem === 'vilhelm'">
      <!-- Replace with your actual component -->
      <p>Content for Vilhelm</p>
    </div>
    <div v-if="selectedItem === 'mor-gitte'">
      <!-- Replace with your actual component -->
      <p>Content for Mor Gitte</p>
    </div>
  </div>
</template>
