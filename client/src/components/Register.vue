<template>
<div>
  <h1>Register</h1>

  <input 
    type="email"
    name="email"
    v-model= "email"
    placeholder="email"/>
  <br>
  <input 
    type="password"
    name="password"
    v-model= "password"
    placeholder="password"/>
    <br>
    <button @click="register">
      Register</button>
</div>
 </template>

<script> //controller 
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register(){
      await AuthenticationService.register({ // const response =
        email: this.email,
        password: this.password
      })
      console.log(response.data)// const response = await sa taas para ma debug
    }
  },
  // watch:{
  //   email (value){
  //     console.log('email has changed value', value)
  //   }
  // },
  // mounted(){
  //   setTimeout(() => {
  //     this.email = 'hello world'
  //   },1000)
  // }
}
</script>

<style scoped>

</style>
