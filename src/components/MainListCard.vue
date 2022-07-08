<template>
    <div class="container">
        <div class="list-container">
           <div class="album-list flex">
               <MainAlbum v-for="element,index in cardList" :key="index" :featuresAlbum="element"/>
           </div>
        </div>
    </div>
</template>

<script>
// import axios from 'axios';
import MainAlbum from './MainAlbum.vue'
import axios from 'axios';


export default {
    name: 'MainListCard',
    
    components:{
        MainAlbum,
    },
    data(){
        return{
            url: 'https://flynn.boolean.careers/exercises/api/array/music',
            cardList: [],
            
        }  
    },
    created(){
        this.reCall()
    },
    methods:{  
    reCall(){
        axios.get(this.url).then((result) => {
            this.cardList = result.data.response
            console.log(result)
        })

    },
    

  }

}
</script>

<style lang="scss" scoped>
@import '../style/common';
@import '../style/variables';
.list-container{
    width: 80%;
    margin: 0 auto;
    padding: 20px 0;
}
.album-list.flex{
    flex-wrap: wrap;
    
}
</style>