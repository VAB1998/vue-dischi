<template>
    <select name="select_genre">
        <option value="all">All</option>
        <option :value="genreList"></option>
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