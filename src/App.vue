<script setup>
import { RouterLink, RouterView, useRoute } from 'vue-router'
import { ref } from 'vue'
import Header from './components/Header.vue'
import { computed } from '@vue/reactivity';

const route = useRoute();
const isLogin = ref(false);
const pth = computed(() => route.path)
</script>

<template>
  <Header>
     
  </Header>
    <div style="float: right;">
        <RouterLink v-show="pth !== '/login'" to="/login" style="padding-right: 12px; text-decoration: none;">
          Login
        </RouterLink>
        <RouterLink v-show="pth !== '/create_account'" to="/create_account" style="padding-right: 12px; text-decoration: none;">
          Create Account
        </RouterLink>
        <RouterLink to="/about" style="padding-right: 12px; text-decoration: none;">
          About
        </RouterLink>
    </div>
  <RouterView />
</template>

<style>
</style>
<style>
    @import "bootstrap/dist/css/bootstrap.css";
    @import "bootstrap-icons/font/bootstrap-icons.css";
</style>
