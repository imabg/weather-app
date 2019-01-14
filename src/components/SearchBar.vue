<template>
  <div>
    <input id="input" v-model = "value" placeholder="city..."/>
    <i class="fa fa-search" @click = "getValue"></i>
  </div>

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
    font-size: 18px;
    border: none;
    font-family: cursive;
    text-align: center;
    outline: none;
    color: blueviolet;
    display: inline-block;
    width: 50%;
  }
  i {
    font-size: 22px;
    cursor: pointer;
    padding: 0;
    margin: 0;
  }
</style>
