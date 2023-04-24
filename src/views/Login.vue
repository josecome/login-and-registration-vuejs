<script setup>
import Form from '../components/Form.vue'


  const auth_store = useStoreAuth()
  const {  isLoggedin, LoginUser, UserName } = storeToRefs(auth_store)

function submit (email, password) {

  return isLoggedin ?  UserName : LoginUser(email, password)  
}
</script>

<template>
  <main>
    <Form
        @submit-form="submit" 
    />
  </main>
</template>
