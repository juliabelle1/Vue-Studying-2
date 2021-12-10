<template>
<div class="container">
<nav class="navbar navbar-expand-lg navbar-light bg-light mb-5">
  <Display :name="name" :text="text" @logoutold-user='logoutOldUser'/>
</nav>
  <Uppdate :name="name" :text="text" @login-user="loginUser" />
</div>
</template>

<script>
import Display from './components/Display.vue'
import Uppdate from './components/Uppdate.vue'

export default {
  name: 'App',
  components: {
    Display,
    Uppdate
  },
  data(){
    return{
      name: '',
      password: '12345',
      text : 'login'
    }
  },
  methods:{
    loginUser(newUser){
      this.name = 'Hello ' + newUser.name,
      this.password = newUser.password,
      this.text = 'log out'
    },

    logoutOldUser(oldUser){
      this.name = oldUser.name,
      this.text = oldUser.text
    }
    
  }
}
</script>

<style>

</style>
