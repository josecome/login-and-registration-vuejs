<script setup>
import Form from '../components/Form.vue'

const submit = () => console.log('Successfully tested!')
</script>

<template>
  <main>
    <Form
        @submit-form="submit" 
    />
  </main>
</template>
