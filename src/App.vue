<template>
  <div class="App">
    <GameGraphics />
  </div>
</template>

<script setup lang="ts">
import GameGraphics from './gamegraphics/GameGraphics.vue';
</script>

<style>
body {
  font: 14px/1.5 sans-serif;
  background: #eee;
}
.App {
  width: 600px;
  margin: 32px auto;
}
.small {
  font-size: 80%;
}
</style>
