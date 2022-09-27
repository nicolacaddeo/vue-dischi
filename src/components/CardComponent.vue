<template>
  <div id="card">
    <img :src="coverUrl" alt="">
    <h3 class="song-title">{{ songTitle }}</h3>
    <p class="artist">{{ artist }}</p>
    <p class="year">{{ year }}</p>
  </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: {
        coverUrl: String,
        songTitle: String,
        artist: String,
        year: String
    }
}
</script>

<style scoped lang="scss">
@import '../style/global_variables.scss';

#card{
  width: calc(100% / 5 - $card-margin * 2);
  text-align: center;
  color: #fff; 
  background-color: $component-color;
  margin: 1rem;
  padding: 1.5rem .5rem;
  img {
    width: 150px;
    height: 150px;
    margin-bottom: $card-margin;
  }
  p {
    color: $song-info-color;
  }
  .song-title{
    text-transform: uppercase;
    margin-bottom: 1rem;
  }
  .artist {
    font-size: 1.2rem;
    text-transform: capitalize;
  }
}

</style>
    