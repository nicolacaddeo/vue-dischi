<template>
    <div>
        <label for="select-genre">Seleziona un genere:</label>
        <select id="select-genre" v-model="searchedGenre" @change="$emit('select', searchedGenre)">
            <option value="none"> - </option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
        
    </div>
</template>

<script>
export default {
name: 'SelectComponent',
data() {
    return{
        searchedGenre: ''
    }
}
}

</script>

<style scoped lang="scss">
   label {
    color: #fff;
    padding-right: 1rem;
   }
   select {
    padding: .3rem 1rem;
    text-align: center;
   }
</style>