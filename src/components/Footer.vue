<template>
    <div class="footer">
        <div class="text">Made by Jo and Lee</div>
    </div>
</template>

<script>
export default {
    name: 'Footer',
    props: {
        
    },
}
</script>

<style scoped>
.footer {
    width: 100%;
    height: 3vh;
    z-index: 1;
    position: relative;
    background: #f0f0f0;
    justify-items: center;
    align-items: center;
    
}
.text {
    margin: 1vh;
    font-family: 'Nanum Brush Script', cursive;
    font-style: italic;
    font-size: 2vh;
}
</style>