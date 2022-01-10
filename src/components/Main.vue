<template>
    <main>
        <div class="container">
            <div class="card-contain">
                <DiscCard v-for="element, index in discListArray" :key="index" :contentOfCard="element"/>
            </div>
        </div>
    </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";
import axios from "axios";

export default {
    name:"Main",
    components: {
        DiscCard
    },
    data: function() {
        return {
            discListArray: []
        };
    },
    methods: {
        getDiscs: function () {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
                this.discListArray = response.data.response
            })
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

    .card-contain {
        display: flex;
        flex-wrap: wrap;
    }
}
</style>