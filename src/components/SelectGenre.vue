<template>
    <select id="select_genre" name="select_genre"> <!-- oppure v-on:change="passa il valore della select" -->

        <!-- <option value="all"  v-on:click="$emit('selectGenre', 'all')">All</option> -->

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

<style lang="scss" scoped>
@import '../style/general.scss';
@import '../style/variables.scss';

#select_genre{
    // Style
    background-color: $main_color;
    border: none;
    //Text Style
    color: $main_color_text;
    font-family: $secondary_font;
    font-size: 1.5rem;
    // Spacing and Dimensions
    width: 40%;
    //Other Settings
    cursor: pointer;
}
</style>