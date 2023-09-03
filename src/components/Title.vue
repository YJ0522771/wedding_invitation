<template>
    <div class="title">
        <img src = "@/assets/contents/title.jpg" class="img"/>
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
    margin: 0;
    z-index: 1;
    position: relative;
}
.img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
</style>