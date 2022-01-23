<script setup lang="ts">
import { ref } from 'Vue';

const fontSize = ref(16);
const text = ref('This is message which you can change')
</script>

<template>
  <div class="center">
    <p
      v-bind:style="{ fontSize: fontSize + 'px' }"
    >{{ text ? text : 'write something, please' }} - size {{ fontSize }}</p>
  </div>
  <div>
    <label for="text">Text</label>
    <textarea type="text" v-model="text" id="text" />
    <label for="font">Text</label>
    <input type="range" class="range" min="2" max="60" step="2" v-model="fontSize" id="font" />
  </div>
</template>

<style scoped>
p {
  margin: 0;
}

.center {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50vh;
  background-color: aliceblue;
}
</style>
