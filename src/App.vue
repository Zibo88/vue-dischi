<template>
  <div id="app">
    <header>
      <MyHeader/>
    </header>

    <main>
      <MainListCard/>
    </main>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MainListCard from './components/MainListCard.vue';


export default {
  name: 'App',
  components: {
    MyHeader,
    MainListCard,

  }
}
</script>

<style lang="scss">
@import './style/common';
@import './style/variables';

</style>
