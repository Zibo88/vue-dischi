<template>
    <div class="single-album">
        <img :src="featuresAlbum.poster" alt="">  
        <h3 class="title">{{featuresAlbum.title}}</h3>
        <div class="author">{{featuresAlbum.author}}</div>
        <div class="date">{{featuresAlbum.year}}</div>
    </div>
</template>

<script>
export default {
    name:'MainAlbum',
     props: {
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
    // test
    background-color: #2d3a46;
    
    img{
        max-height: 200px;
        overflow: hidden;
    }

    h3{
        color: white;
        text-align: center;
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