<script setup>
import { RouterLink, RouterView, useRoute } from 'vue-router'
import { ref, onMounted, watch } from 'vue'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import { computed } from '@vue/reactivity';
import { useStoreAuth } from '@/stores/auth_store'
import { useRouter } from 'vue-router'
import { storeToRefs } from 'pinia'

const route = useRoute();
const router = useRouter()
const pth = computed(() => route.path)
const auth_store = useStoreAuth()
const {  isLoggedin } = storeToRefs(auth_store)
watch(isLoggedin, () => isLoggedin.value ? router.push({ name: 'home' }) : '' )
onMounted(() => { 
  auth_store.LoginUserByToken() 
  isLoggedin.value ? router.push({ name: 'home' }) : ''
})

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
    </div>
  <RouterView />
  <Footer />
</template>

<style>
</style>
<style>
    @import "bootstrap/dist/css/bootstrap.css";
    @import "bootstrap-icons/font/bootstrap-icons.css";
</style>
