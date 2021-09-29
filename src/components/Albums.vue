<template>
    <section id="albums">
        <div class="container">
            <div class="g-5 row row-cols-2 row-cols-md-3 row-cols-lg-5">
                <Album  v-for="(item, index) in albumList" :key="index"
                :imageSource="item.poster" :albumTitle="item.title" :author="item.author" :year="item.year" />
            </div>
        </div>
    </section>
</template>

<script>
import Album from './Album.vue'
import axios from 'axios'
export default {
    name: 'Albums',

    components: {
        Album
    },

    data : function(){
        return{

            albumList : []


        }
    },

    created : function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((object) =>{
            console.clear()
            //Take the Datas from the API and put them into the array (using slice)
            this.albumList =  object.data.response.slice()
            
            //Check
            console.log(object)
            console.log(object.data)
            console.log(object.data.response)
            console.log(object.data.response[0])
            console.log(object.data.response[0].author)
        })
    } 
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
@import '../style/variables.scss';

#albums{
    margin-top: 100px;
}
</style>