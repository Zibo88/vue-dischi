<template>
    <div>
        <!-- leggo il valore della value attraverso la variabile userValue, invio i dati al padre tramite emit(nome ancoraggio, dato necessario per definire il genere musicale) -->
        <select v-model="userValue" @change="$emit('research', userValue)" id="music-genres" >
            <option value="all">all</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="metal">Metal</option>
            <option value="jazz">Jazz</option>
        </select>
    </div>
</template>

<script>

export default {
    name: 'MyBarr',
    data(){
        return{
            userValue: 'all',
        }
    }
    // methods:{
    //     researchAlbum(){
    //         this.$emit('research', 'type')
    //         console.log(this)
    //     }
    // }

}
</script>

<style lang="scss" scoped>

</style>