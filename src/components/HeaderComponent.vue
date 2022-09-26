<template>
  <div id="header">
    <img src="../assets/logo.svg" alt="logo spotify">
  </div>
</template>

<script>
export default {
    name: 'HeaderComponent'
}
</script>

<style scoped lang="scss">
@import '../style/global_variables.scss';

#header {
    position: fixed;
    width: 100%;
    height: 7vh;
    padding: 1rem;
    display: flex;
    align-items: center;
    background-color: $component-color;
    img {
        width: 50px;
    }
}
</style>