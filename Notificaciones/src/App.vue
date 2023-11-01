<script setup>
import { ref } from 'vue'

let notifications = ref(0)

function addValue() {
  notifications.value++
  console.log(notifications)
}

function minusValue() {
  if (notifications.value > 0) {
    notifications.value--
  }
}
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="notification" v-if="notifications > 0">{{ notifications }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="minusValue">-</div>
      <div class="button" @click="addValue">+</div>
    </div>

    <div v-if="notifications > 0">Revisa tu inbox</div>
    <div v-else>No tienes notificaciones</div>
  </div>
</template>

<style scoped>
.wrapper {
  background-color: wheat;
  width: 60%;
  border-radius: 8px;
  margin: 0 auto;
  padding-top: 32px;
}

.profile {
  background-color: purple;
  background-image: url(https://www.mundodeportivo.com/files/og_thumbnail/uploads/2018/10/24/60e7ed59bd621.jpeg);
  background-size: cover;
  width: 120px;
  height: 120px;
  border-radius: 100%;
  margin: 0 auto;
  margin-top: 0;
  position: relative;
}

.notification {
  position: absolute;
  background-color: red;
  width: 18px;
  height: 18px;
  border-radius: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  top: 0;
  right: 0;
}

.button-wrapper {
  margin: 0;
  padding: 16px;
  align-items: center;
}

.button {
  background-color: peru;
  border-radius: 4px;
  padding: 2px 6px;
  font-weight: bold;
  color: white;
  display: inline-block;
  width: 40px;
  cursor: pointer;
  margin: 0 20px;
}
</style>
