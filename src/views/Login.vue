<template>
  <v-app class="login"> 
    <div>
      <v-content>
        <Login/>
      </v-content>
    </div>
  </v-app>
</template>

<script>
  import Login from '../components/Login'

  export default {
    components: {
      Login
    }
  }
</script>
<style scoped>
.login {
    background-color: #082767;
    background-image: url("../assets/background.jpeg");
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
}
</style>
