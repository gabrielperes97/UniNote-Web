<template>
<input type="text" v-model="text"/>
</template>

<style lang="sass" scoped>

</style>

<script>
export default {
  name: "click-edit",
  props: ['text'],
  data() {
    return {
        text: "teste",
        showPassword: false
    };
  }
};
</script>
