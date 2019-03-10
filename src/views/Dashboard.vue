<template lang="html">
<v-app class="Dashboard">
  <v-container grid-list-lg fluid>
    <v-layout row wrap>
      <v-flex xl3 lg3 md4 sm6 xs12 class="note">
        <Note />
      </v-flex>
      <v-flex xl3 lg3 md4 sm6 xs12>
        <Note />
      </v-flex>
      <v-btn
        fixed
        dark
        fab
        bottom
        right
        color="pink"
        class=""
      >
        <v-icon>add</v-icon>
      </v-btn>
    </v-layout>
  </v-container>
  </v-app>
</template>

<style lang="sass" scoped>
</style>

<script lang="ts">
import Vue from 'vue';
import Note from '../components/Note.vue';

export default Vue.extend({
  components: {
    Note,
  },
});
</script>
