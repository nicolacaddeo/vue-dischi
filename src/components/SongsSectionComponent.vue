<template>
  <section id="songs"> <!-- Contenitore delle cards -->
    <div class="search-container">
        <SelectComponent @select="selectGenre" />
    </div>
    <div class="container">
        <CardComponent v-for="song, i in genreToDisplay" :key="song" 
        :coverUrl = genreToDisplay[i].poster
        :songTitle = genreToDisplay[i].title 
        :artist = genreToDisplay[i].author
        :year = genreToDisplay[i].year />
    </div>
  </section>
</template>

<script>
import axios from "axios";
import CardComponent from './CardComponent.vue';
import SelectComponent from "./SelectComponent.vue";

export default {
    name: 'SongSection',
   components: {
    CardComponent,
    SelectComponent
    },
    data() {
        return {
            songs: [],
            genreToDisplay: []
        }
    },
    methods: {
        selectGenre(selectedGenre) {
            console.log(selectedGenre);
            const newArray = [];
            this.songs.forEach((item)=> {
                if(item.genre.indexOf(selectedGenre) > -1) {
                    newArray.push(item);
                }
            })
            this.genreToDisplay = newArray;
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(({status, data})=> {
            if (status === 200) {
                this.songs = data.response;
                this.genreToDisplay = data.response;
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
.search-container {
    margin-bottom: 2rem;
    width: 60%;
    margin: 0 auto;
    padding-left: 1rem;
}
</style>