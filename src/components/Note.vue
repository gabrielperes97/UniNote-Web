<template>
<v-app class="note">
    <v-card>
        <v-card-title primary-title>
            <div>
                <h3>
                    Título
                </h3>
                Teste
            </div>
        </v-card-title>
    </v-card>
</v-app>
</template>

<style lang="sass" scoped>
.note
    width: 100%
</style>


<script lang="ts">
import Vue from "vue";
export default Vue.extend({
    name: "note-component",
    data() {
    return {
      showPassword: false
    };
  }
});
</script>
