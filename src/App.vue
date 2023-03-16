<template>
  <MainHeader />
  <LoginForm />
  <!-- <SignForm /> -->
</template>

<script>
import { useSanityClient } from 'vue-sanity'
// import SignForm from './components/user/SignForm.vue'
import MainHeader from './components/MainHeader.vue'
// import UpdateUserInfo from './components/MainHeader.vue'
import LoginForm from './components/user/LoginForm.vue'

export default {
  name: 'App',
  setup() {
    useSanityClient(
      {
        projectId: 'ujf74srv',
        dataset: 'production',
        useCdn: false,
        token: process.env.SANITY_AUTH_TOKEN,
        apiVersion: "2021-10-21"
      }, 
      // true    // will not create a preview client for use elsewhere
      )
    },
  components: {
    // SignForm,
    MainHeader,
    // UpdateUserInfo
    LoginForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  margin: 0;
  background:  #eee;
}
</style>
