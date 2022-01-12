<template>
    <main>
        <div class="container">
            <div v-if="!successLoad" class="card-contain">
                <DiscCard v-for="element, index in filteredDiscs" :key="index" :contentOfCard="element"/>
            </div>
            <Loader v-else/>
        </div>
    </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";
import Loader from "./Loader.vue";
import axios from "axios";

export default {
    name:"Main",
    components: {
        DiscCard,
        Loader
    },
    props: {
        filterGenre: String
    },
    data: function() {
        return {
            discListArray: [],
            successLoad: true,
            genresList: []
        };
    },
    methods: {
        getDiscs: function () {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
                this.discListArray = response.data.response,
                this.discListArray.forEach((element) => {
                    if(!this.genresList.includes(element.genre)) {
                       this.genresList.push(element.genre); 
                    }
                });
                this.$emit('genresListCreated', this.genresList);
                this.successLoad = false
            })
        }
    },
    computed: {
        filteredDiscs: function() {
            if(this.filterGenre === '') {
                return this.discListArray;
            }
            let filteredArray = [];
            filteredArray = this.discListArray.filter((element) => {
                return element.genre === this.filterGenre;
            });
            return filteredArray;
        }
    },
    created: function() {
        this.getDiscs()
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables";
main {
    padding-top: 30px;
    height: calc(100vh - 50px);
    background-color: $main-color;
    color: white;
    overflow: auto;

    .card-contain {
        display: flex;
        flex-wrap: wrap;
    }
}
</style>