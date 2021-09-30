<template>
    <select name="select_genre"> <!-- oppure v-on:change="passa il valore della select" -->
        <option value="all"  v-on:click="$emit('selectGenre', 'all')">All</option>

        <option v-for="(genreItem, index) in genreList" :key="index" 
        v-on:click="$emit('selectGenre', genreItem)" :value="genreItem"> {{genreItem}} </option>
    </select>
</template>

<script>
export default {
name: 'SelectGenre',

props : {
    genreList : Array
},
}
</script>

<style>

</style>