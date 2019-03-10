<template>

<v-card >
    <v-card-title primary-title>
        <h3 class="headline mb-0">
            <input type="text" v-model="titulo"/>
        </h3>
    </v-card-title>
    <v-card-text>
        <div contentEditable="true" class="content">{{text}}</div>
    </v-card-text>
</v-card>

</template>

<style lang="sass" scoped>
.content
    display: block;
    overflow-y: auto;
</style>


<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'note-component',
  data() {
    return {
      titulo: 'Títulos',
      text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
    };
  },
});
</script>
