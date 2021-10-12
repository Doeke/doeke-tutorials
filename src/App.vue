<template>
  <div class="App">
    <GameGraphics />
  </div>
</template>

<script setup lang="ts">
import GameGraphics from './gamegraphics/GameGraphics.vue';
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@400;900&display=swap');
body {
  font: 18px/1.4 'Lato', sans-serif;
  background: #eee;
}
.App {
  width: 800px;
  margin: 32px auto 250px;
}
h1, h2 {
  font-size: 32px;
  margin-top: 32px;
}
h2 {
  font-size: 120%;
}
</style>
