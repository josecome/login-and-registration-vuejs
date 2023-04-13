<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
    <div>
        <RouterLink to="/">Login</RouterLink>
        <RouterLink to="/about">About</RouterLink>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
  header {
    float: top;
    width: 100%;
  }
</style>
<style>
    @import "bootstrap/dist/css/bootstrap.css";
    @import "bootstrap-icons/font/bootstrap-icons.css";
</style>
