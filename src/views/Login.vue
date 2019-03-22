<template>
  <v-app class="login">
  <v-container grid-list-xl text-xs-center>
    <v-layout row wrap>
      <v-flex xl4 offset-xl4 lg4 offset-lg4 md6 offset-md3 sm8 offset-sm2 xs12>
        <Login/>
      </v-flex>
    </v-layout>
  </v-container>
  </v-app>
</template>

<script>
import Login from '../components/Login.vue';

export default {
  components: {
    Login,
  },
};
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
