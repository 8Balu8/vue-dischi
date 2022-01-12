<template>
    <header>
        <img src="https://thumbs.dreamstime.com/b/modalit%C3%A0-scura-logo-spotify-vinnytsia-ucraina-maggio-un-servizio-di-musica-cool-che-offre-flusso-streaming-legale-218033923.jpg" alt="Spotify Logo">
        <div>
            <label for="genre">Select Genre</label>
            <select v-model="selectGenre" id="genre" @change="$emit('selectChanged', selectGenre)">
                <option value="">All</option>
                <option v-for="(genre, index) in genres" :key="index" :value="genre">{{ genre }}</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
    props: {
        genres: Array
    },
    data: function() {
        return {
            selectGenre: ''
        };
    }
}
</script>

<style lang="scss" scoped>
header {
    height: 50px;
    padding: 20px;
    background-color: black;
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: white;

    label {
        margin-left: 30px;
        margin-right: 10px;
    }

    img {
        height: 30px;
    }
}
</style>