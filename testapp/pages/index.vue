<template>
  <div class='app'>
    <div v-if="!this.status">
      <loginForm @login="login"/>
    </div>
    <div v-else>
      <Profile :username="username" @login="login"/> 
    </div>
    
    
  </div>
</template>

<script>
import LoginForm from '~/components/LoginForm.vue';
import Profile from '~/components/Profile.vue';

export default {
  name: 'app',
  data () {
    return {
      status: false,
      username: ""
    }
  },
  methods: {
    login (username) {
      this.status = !this.status
      this.username = username
      console.log(username)
    }
  },
  components : {
    loginForm:LoginForm,
    Profile
  }
}

</script>

<style lang="scss">

</style>