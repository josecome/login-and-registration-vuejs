<script setup>
    import Logo from "@/assets/logo.svg";
    import { useRoute } from 'vue-router'
    import { computed } from '@vue/reactivity';

    const route = useRoute();
    const pth = computed(() => route.path)
</script>
<template>
    <div id="header" style="width: 100%;">
        <a href="/"><img :src="Logo" alt="Logo" /></a>
        <a v-show="pth !== '/logout'" href="/logout" style="float: right; text-decoration: none; padding-right: 10px;">Logout</a>
    </div>
</template>
<style scoped>
    img {
        float: left;
        width: 60px;
        height: 60px;
    }
</style>