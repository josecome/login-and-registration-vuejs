<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import Header from './components/Header.vue'
import { computed } from '@vue/reactivity';

const isLogin = ref(false);
computed(() => this.$route.path === '/login'? isLogin : !isLogin)
computed(() => this.$route.path === '/logout'? alert('User Logged out!') : '')
</script>

<template>
  <Header>
     
  </Header>
    <div>
        <RouterLink v-show="!isLogin" to="/login">Login</RouterLink>
        <RouterLink to="/about">About</RouterLink>
    </div>
  <RouterView />
</template>

<style>
</style>
<style>
    @import "bootstrap/dist/css/bootstrap.css";
    @import "bootstrap-icons/font/bootstrap-icons.css";
</style>
