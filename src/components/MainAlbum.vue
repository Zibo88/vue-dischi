<template>
    <!-- creo struttura della singola card -->
    <div class="single-album">
        <!-- elementi dentro la card -->
        <img :src="featuresAlbum.poster" alt="">  
        <h3 class="title">{{featuresAlbum.title}}</h3>
        <div class="author">{{featuresAlbum.author}}</div>
        <div class="date">{{featuresAlbum.year}}</div>
    </div>
</template>

<script>
export default {
    // definisco il nome del componente che verrà importato nel componenete che dovrà poi stamparlo
    name:'MainAlbum',
    // passo tramite props all'elemento genitore tutte le caratteristiche relativa alla card, derivanti dal response.data(console.log(result) vedi funzione reCall() in MainListCard.vue), in questo caso un oggetto. In MainList.vue :featuresAlbum sarà = al nome usato per ciclare un array con v-for così da avere il singolo elemento
     props: {
        //  sarà l'oggetto che verrà passato alla lista e sarà uguale a element del v-for
        featuresAlbum: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/common';
@import '../style/variables';
.single-album{
    width: calc((100% / 5) - 32px);
    margin: 16px;
    background-color: #2d3a46;
    
    img{
        max-height: 170px;
        overflow: hidden;
    }

    h3{
        color: white;
        text-align: center;
    }
    &:hover{
        transform: scale(1.2);
    }
}

.date, .author {
    text-align: center;
    color: $subtitle_color;
    margin: 5px;
}

h3, .date, .author{
    padding: 0 10px;
}
</style>