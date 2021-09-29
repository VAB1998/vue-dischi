<template>
    <section id="albums">
        <div class="container">
            <Album  v-for="(item, index) in albumList" :key="index"/>
            
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


</style>