<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="star"
          aria-label="Menu"
          @click="showStarTips"
        />

        <q-toolbar-title> Quasar Enhanced Counter </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-dialog v-model="starTips" persistent>
      <q-card class="text-white q-dialog-card">
        <q-card-section class="text-center">
          <h5 class="q-ma-sm">
            Click and Hold the buttons or Click and Drag up and down to operate
            the counter!
          </h5>
        </q-card-section>
        <q-card-actions align="right">
          <q-btn flat label="Close" class="close-btn" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <q-img src="background.jpg" class="fit absolute" />

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

const starTips = ref(false)

const showStarTips = () => {
  starTips.value = !starTips.value
}
</script>

<style scoped>
.q-dialog-card {
  background-color: #292dae; /* Nice decent background color */
  color: white;
}

.close-btn {
  background-color: white;
  color: var(--q-primary);
  border: 1px solid var(--q-primary);
  text-transform: none;
  padding: 8px 16px;
}
</style>
