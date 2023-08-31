<template>
    <div class="information">
        <img src = "@/assets/contents/information.jpg" class="img"/>
    </div>
</template>

<script>
export default {
    name: 'Information',
    props: {
        
    }
}
</script>

<style scoped>
.information {
    width: 100%;
    margin: 0;
}
.img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
</style>