<template>
  <div id="app">
    <header>
      <HeaderComponent />
    </header>
    <main>
      <SongSection />
    </main>
  </div>
</template>

<script>
  import HeaderComponent from './components/HeaderComponent.vue';
  import SongSection from './components/SongsSectionComponent.vue';
  
  export default {
  name: 'App',
  
  components: {
    HeaderComponent,
    SongSection
  }
}
</script>

<style lang="scss">
  @import './style/main.scss';
  @import './style/global_variables.scss';
  
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
    
  

  
      
