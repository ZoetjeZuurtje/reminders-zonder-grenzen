<script setup lang="ts">
import Header from './components/Header.vue'
import Countdown from './components/Countdown.vue'
const targetDate = new Date('2026-05-13T18:00:00Z');
</script>

<template>
  <div>
    <Header />

    <main id="center">
      <div>
        <h2>Je gaat die boekenlegger meenemen.</h2>
        <p class="lead">Ik heb alle vertrouwen in je</p>
      </div>

      <Countdown :target='targetDate'/>
    </main>
  </div>
</template>
