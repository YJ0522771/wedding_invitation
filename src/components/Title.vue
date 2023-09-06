<template>
    <div class="title">
        <img src = "@/assets/contents/title.png" class="img"/>
    </div>
</template>

<script>
export default {
    name: 'Title',
    props: {
        
    }
}
</script>

<style scoped>
.title {
    width: 100%;
    height: 100vh;
    margin: 0;
    margin-bottom: 20vw;
    z-index: 1;
    position: relative;
    background: #b9DeDb;
}
.img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
</style>