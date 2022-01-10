<template>
    <div class="card">
        <img src="https://img.discogs.com/vknPDdrqRbT92pNRX0W4I5N91jg=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-1246953-1448927086-6590.jpeg.jpg" alt="">
        <div class="title">
            Sono il titolo
        </div>
        <div class="disc-info">
            Author
        </div>
        <div class="disc-info">
            Year
        </div>
    </div>
</template>

<script>
export default {
    name: "DiscCard"
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
        margin: 10px 0;
    }

    .disc-info {
        color: gray;
    }
}

</style>