<template>
    <div class="title">
        <h3>Title</h3>
        <img src = "@/pictures/01.jpg" class="img"/>
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
}
.img {
    width: 100%;
    object-fit: contain;
}
</style>