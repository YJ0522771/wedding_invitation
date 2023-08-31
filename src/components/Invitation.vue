<template>
    <div class="invitation">
        <img src = "@/assets/contents/invitation.jpg" class="img"/>
    </div>
</template>

<script>
export default {
    name: 'Invitation',
    props: {
        
    }
}
</script>

<style scoped>
.invitation {
    width: 100%;
    margin: 0;
}
.img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
</style>