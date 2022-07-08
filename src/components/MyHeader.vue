<template>
<!-- creo la struttura html del componente header -->
  <div class="header-barr">
      <img src="../assets/logo-small.svg" alt="logo img">
  </div>
</template>

<script>
export default {
    // definisco il componente
    name:'MyHeader'
}
</script>

<style lang="scss" scoped>
.header-barr{
    background-color: #2d3a46;
    img{
        width: 30px;
        margin: 5px 0;
        padding-left: 5px;
    }
}
</style>