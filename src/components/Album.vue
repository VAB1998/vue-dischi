<template>

        
        <div  class="col text-center">
            <div class="album p-2 h-100">

                <img class="w-100" :src="imageSource" :alt="author">
                <h2 class="albumTitle"> {{albumTitle}} </h2>
                <span class="author"> {{author}} </span>
                <span class="year"> {{year}} </span>

            </div>
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

.album{
    background-color: $main_color;

    .albumTitle{
        color: $main_color_text;
    }    
    .author,
    .year{
        display: block;
        color: $secondary_color_text;
    }

    
}

</style>