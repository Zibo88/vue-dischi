<template>
    <div class="container">
        <!-- creo la sezione relativa alla lista di album -->
        <section class="list-container">
           <MyBarr @research="searchGender"/>
           <div class="album-list flex">
               <!-- 1.1utilizzo la singola card
                 caso v-for: ne creo tante quante sono presenti all'interno dell'array cardList precedentemente riempito con tramite l'url di axios.get() richiamato con la funzione reCall()  -->
               <MainAlbum  v-for="element,index in cardList" :key="index" :featuresAlbum="element" />
           </div>
        </section>
    </div>
</template>

<script>
// importo la card
import MainAlbum from './MainAlbum.vue'

// importo axios dove poi dovrò stampare la lista di card
import axios from 'axios';

// importo la barra di ricerca
import  MyBarr from './MyBarr.vue'


export default {
    // definisco il componenete dove verranno stampati altri componenti
    name: 'MainListCard',
    
    
    components:{
        // la definisco come singolo componente card
        MainAlbum,
        MyBarr
    },
    data(){
        return{
            // url axios (era possibile mettere il link axios direttamente nella funzione reCall() al posto di this.url) 
            url: 'https://flynn.boolean.careers/exercises/api/array/music',
            // array vuoto che mi servirà per avere un array di oggetti da poter riempire con (this.arrayVuoto = result.data.(console.log(result)))
            cardList: [],
            arrayFiltred:[],
            choice:'all'
        }  
        
    },
    computed:{
      genersFiltred(){
        if(this.choice == 'all'){
            return this.cardList
        }
       if(this.choice == 'pop'){
           return this.arrayFiltred
       }
       return this.arrayFiltred
      }
    
    },

    // richiamo la funzione così che sia creata
    created(){
        this.reCall()
    },
    methods:{  
        // definisco la funzione che mi servirà per richiamare axios
    reCall(){
        // richiamo il link necessario per axios
        axios.get(this.url).then((result) => {
            // l'array sarà riempito dal response (in questo caso array/data/response vedi console.log di result) presente nell'array di oggetti dell'url
            this.cardList = result.data.response
            // valutazione del contenuto della chiamta axios
            console.log(result)

            // controllo all'interno degli album i generi che sono presenti. Se non sono gia presenti vengono pushati
            // all'interno dell'array Filtrato
             this.cardList.forEach(element => {
                if(!this.arrayFiltred.includes(element.genre)){
                    this.arrayFiltred.push(element.genre)
                }
            });
            console.log(this.arrayFiltred)
           
        })

    },
    searchGender(choice){
       this.userValue = choice
       console.log('choice',choice)
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