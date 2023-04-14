<script setup>
    import Logo from "@/assets/logo.svg";
</script>
<template>
    <div id="header" style="width: 100%;">
        <img :src="Logo" alt="Logo" />
        <a href="/logout" style="float: right; text-decoration: none; padding-right: 10px;">Logout</a>
    </div>
</template>
<style scoped>
    img {
        float: left;
        width: 60px;
        height: 60px;
    }
</style>