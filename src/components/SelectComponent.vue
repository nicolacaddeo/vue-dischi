<template>
    <div>
        <label for="select-genre">Seleziona un genere:</label>
        <select id="select-genre" v-model="searchedGenre" @change="$emit('select', searchedGenre)">
            <option value="none"> - </option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
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