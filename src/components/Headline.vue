<template>
    <div class="headline">
        <img src="@/assets/icons/L.png" class="img">
        <span class="text">
            {{ headline }}
        </span>
        <img src="@/assets/icons/J.png" class="img">
    </div>
</template>

<script>
export default {
    name: 'Title',
    props: {
        headline:String,
    }
}
</script>

<style scoped>
.headline {
    width: 100%;
    margin: 5vw auto;
    z-index: 1;
    position: relative;
    align-content: center;
    justify-content: center;
}
.img {
    width: 7vw;
    height: 7vw;
    margin: auto 3vw;
    display: inline-flex;
}
.text {
    width: 35vw;
    font-size: 1.2rem;
    font-weight: bold;
    margin: 2vw auto;
    display: inline-flex;
    text-align: center;
    align-content: center;
    justify-content: center;

    font-family: 'Gamja Flower', cursive;
}
</style>