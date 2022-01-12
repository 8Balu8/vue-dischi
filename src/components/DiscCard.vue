<template>
    <div class="card">
        <img :src="contentOfCard.poster" :alt="contentOfCard.author">
        <div class="title">
            {{contentOfCard.title}}
        </div>
        <div class="disc-info">
            {{contentOfCard.author}}
        </div>
        <div class="disc-info">
            {{contentOfCard.year}}
        </div>
        <div class="genre">
            {{contentOfCard.genre}}
        </div>
    </div>
</template>

<script>
export default {
    name: "DiscCard",
    props: {
        contentOfCard: Object
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables";

.card {
    background-color: $card-color;
    width: calc((100% / 5) - 40px);
    margin: 10px 20px;
    padding: 20px;
    text-align: center;

    img {
	    width: 100%;
    }

    .title {
        text-transform: uppercase;
        font-weight: bold;
        font-size: 20px;
        margin-top: 10px;
        margin-bottom: 20px;
    }

    .disc-info {
        color: gray;
    }

    .genre {
        margin-top: 20px;
    }
}

</style>