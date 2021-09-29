<template>

        
        <div  class="album col">
            <img class="w-100" :src="imageSource" :alt="author">
            <h2> {{albumTitle}} </h2>
            <span> {{author}} </span>
            <span> {{year}} </span>
        </div>

        

</template>

<script>
export default {
    props : {
        imageSource : String,
        albumTitle : String,
        author : String,
        year : String
    },
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
@import '../style/variables.scss';


</style>