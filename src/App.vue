<template>
  <div id="app">
    <header>
      <!-- stampo componente dove verrà stampato -->
      <MyHeader/>
    </header>

    <main>
      <!-- 1.1 stampo il componente MainListcard  -->
      <!-- 2 il componente presenta al suo interno un altro componente MainAlbum che verrà di conseguenza stampato a sua volta   -->
      <MainListCard />
    </main>
  </div>
</template>

<script>
// importo i componenti da stampare
import MyHeader from './components/MyHeader.vue';
import MainListCard from './components/MainListCard.vue';


export default {
  name: 'App',
  components: {
    // definisco i componenti che verranno stampati
    MyHeader,
    MainListCard,

  },
  
}
</script>

<style lang="scss">
@import './style/common';
@import './style/variables';

</style>
