<template>
  <div class="card text-center changes" >
  <div class="card-footer text-muted">
    Crafted By <a href="https://github.com/abhay676" target="_blank">Abhay Goswami😎</a>
  </div>
</div>
</template>

<script>
export default {
  props: {
    resPositive: {
      required: true,
      type: Boolean
    }
  }
}
</script>

<style scoped>
  .changes {
    margin-top: 22px;
  }
  
  a {
    text-decoration: none;
  }
</style>
