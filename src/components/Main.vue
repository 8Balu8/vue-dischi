<template>
    <main>
        <div class="container">
            <div class="card-contain">
                <DiscCard/>
                <DiscCard/>
                <DiscCard/>
                <DiscCard/>
                <DiscCard/>
                <DiscCard/>
                <DiscCard/>
            </div>
        </div>
    </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";

export default {
    name:"Main",
    components: {
        DiscCard
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