<template>
    <section id="albums">
        <div class="container">
            <div class="row mb-3">
                <div class="col-12 text-center">
                    <SelectGenre  @selectGenre="select"  :genreList="genreList" /> 
                </div>
            </div>
            <div class="g-5 row row-cols-2 row-cols-md-3 row-cols-lg-4">
                <Album  v-for="(item, index) in filteredAlbumList" :key="index"
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
            genreList : [],
            filteredAlbumList : [],

        }
    },

    methods : {

        /**
         * Pushes the items in an array that are not already in it.
         */
        getUniquePropertyValues(){

            this.albumList.forEach((item) =>{

                if (!this.genreList.includes(item.genre)){

                    this.genreList.push(item.genre);
                }
            })
        },

        /**
         * Selects the objects of the albumList array depending on the given genre
         * @param {string} genreItem The selected genre
         */
        select(genreItem){

            if (genreItem.trim().toLowerCase() === 'all'){
            this.filteredAlbumList = this.albumList.slice();
            } else{
                this.filteredAlbumList = this.albumList.filter((item) => item.genre.trim().toLowerCase() == genreItem.trim().toLowerCase());
            }

            //Checks
            console.clear()
            console.log('Selected Genre: ', genreItem)
            console.log('Filtered Album Luist:', this.filteredAlbumList)
        }
        

    },

    created : function() {
        //Make HTTP  GET Request to an API
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((object) =>{
            console.clear()
            //Take the Datas from the API and put them into the array (using slice)
            this.albumList =  object.data.response.slice()

            this.getUniquePropertyValues()
            //Load the page with a "default" genreItem='all' 
            this.select('all')
            //Check
            console.log('API Datas Response:', object.data.response)

        });
    },

    computed: function(){
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