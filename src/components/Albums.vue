<template>
    <section id="albums">
        <div class="container">
            <div class="row mb-3">
                <div class="col-12 text-center">
                    <SelectGenre  :genreList="genreList" />
                </div>
            </div>
            <div class="g-5 row row-cols-2 row-cols-md-3 row-cols-lg-5">
                <Album  v-for="(item, index) in albumList" :key="index"
                :imageSource="item.poster" :albumTitle="item.title" :author="item.author" :year="item.year" />
            </div>
        </div>
    </section>
</template>

<script>
import Album from './Album.vue'
import SelectGenre from './SelectGenre.vue'
import axios from 'axios'
export default {
    name: 'Albums',

    components: {
        Album,
        SelectGenre
    },

    data : function(){
        return{

            albumList : [],
            genreList : []

        }
    },

    methods : {
        getUniquePropertyValues(){

            this.albumList.forEach((item) =>{
                console.log(item.genre)
            })
            // this.albumList.forEach((item) => !this.genreList.includes(item.genre) ? this.genreList.push(item.genre) : '');
                


            // for(item of this.albumList){

            //     if (!this.genreList.includes(item.genre)){

            //     this.genreList.push(item.genre);
            //     }
            // }
        }
        

    },

    created : function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((object) =>{
            // console.clear()
            //Take the Datas from the API and put them into the array (using slice)
            this.albumList =  object.data.response.slice()
            
            //Check
            // console.log(object)
            // console.log(object.data)
            // console.log(object.data.response)
            // console.log(object.data.response[0])
            // console.log(object.data.response[0].author)
        });

        
    },

    mounted(){
        this.getUniquePropertyValues()
    }

}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
@import '../style/variables.scss';

#albums{
    margin: 100px 0 100px 0;
}
</style>