<template>
  <div
      class="min-h-screen flex items-center justify-center bg-gradient-to-r from-purple-400 via-pink-500 to-red-500"
  >
    <div class="bg-white p-8 rounded-lg shadow-md w-96">
      <transition name="fade" mode="out-in">
        <MessageDisplay :message="message" :key="message" />
      </transition>
      <ToggleButton @toggle="toggleMessage" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import MessageDisplay from "./components/MessageDisplay.vue";
import ToggleButton from "./components/ToggleButton.vue";

const message = ref("Hello!");

const toggleMessage = () => {
  message.value = message.value === "Hello!" ? "Goodbye!" : "Hello!";
};
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
