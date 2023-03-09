<script lang="ts">
import LoginForm from "@/components/form/LoginForm.vue";
export default {
  components: {
    LoginForm,
  },
};
</script>

<template>
  <main>
    <div class="container">
      <LoginForm />
    </div>
  </main>
</template>

<style>
  body {
    background: url("src/assets/bg.png") no-repeat center center fixed;
  }
</style>
