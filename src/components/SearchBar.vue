<template>
  <input id="input" v-model = "value" @keyup.enter = "getValue" placeholder="Enter City Name"/>
</template>

<script>
export default {
  name: 'SearchBar',
  data() {
    return {
        value: ''
    };
  },
  methods: {
    getValue() {
        this.$emit('retieve', this.value);
    }
  }
}
</script>

<style scoped>
  #input {
    font-size: 23px;
    font-family: cursive;
    text-align: center;
  }
</style>
