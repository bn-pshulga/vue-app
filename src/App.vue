<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<template>
  <header>
    <img alt="logo" class="logo" src="@/assets/logo.svg"/>
  </header>
  <RouterView />
</template>

<style scoped>
  header {
    padding: 59px 74px;
  }
</style>
