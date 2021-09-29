<template>

        <div  class="col text-center">
            <div class="album card p-3 h-100">

                <img class="card-img-top" :src="imageSource" :alt="author">
                <div class="card-body pb-0  px-0">
                    <h4 class="albumTitle"> {{albumTitle}} </h4>
                    <span class="author"> {{author}} </span>
                    <span class="year"> {{year}} </span>
                    <a class="stretched-link" href="#"></a>
                </div>
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
    transition: .3s linear;

    .albumTitle{
        color: $main_color_text;
    }  

    .author,
    .year{
        display: block;
        color: $secondary_color_text;
        font-family: $secondary_font;
    }

    &:hover{
        background-color: darken($main_color, 2%)
    }
}

</style>