<template>
  <section id="songs"> <!-- Contenitore delle cards -->
    <div class="container">
        <CardComponent v-for="song, i in songs" :key="song" 
        :coverUrl = songs[i].poster
        :songTitle = songs[i].title 
        :artist = songs[i].author
        :year = songs[i].year />
    </div>
  </section>
</template>

<script>
import axios from "axios";
import CardComponent from './CardComponent.vue';

export default {
    name: 'SongSection',
   components: {
    CardComponent
   },
    data() {
        return {
            songs: []
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(({status, data})=> {
            if (status === 200) {
                this.songs = data.response;
                console.log('songs e\' uguale a:', this.songs);
            }
        })
    }
}
</script>

<style scoped lang="scss">
@import '../style/global_variables.scss';

#songs {
    height: 100vh;
    background-color: $bg-color;
    padding-top: 15vh;
    .container {
        width: 60%;
        height: 70vh;
        margin: 0 auto;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
}
</style>
        
        
        
        