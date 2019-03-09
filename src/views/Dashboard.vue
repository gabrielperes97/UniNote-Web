<template lang="html">
<v-app class="Dashboard">
  <v-container>
    <v-layout row wrap>
      <v-flex xl3 lg3 md6 sm6 xs12>
        <Note/>
      </v-flex>
        <v-btn
        fixed
        dark
        fab
        bottom
        right
        color="pink"
        >
        <v-icon>add</v-icon>
    </v-btn>
    </v-layout>
  </v-container>
  </v-app>
</template>

<style lang="sass" scoped>
.html
    width: 100%
</style>

<script lang="ts">
import Vue from 'vue';
import Note from '../components/Note.vue';
export default Vue.extend({
    components: {
        Note
    }
});
</script>
