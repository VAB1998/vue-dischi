<template>
    <section id="albums">
        <div class="container">
            <Album />
        </div>
    </section>
</template>

<script>
import Album from './Album.vue'

export default {
    name: 'Albums',
    components: {
        Album
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
@import '../style/variables.scss';


</style>