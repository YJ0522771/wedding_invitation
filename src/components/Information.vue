<template>
    <div class="information">
        <img src = "@/assets/contents/information.png" class="img"/>
        <div class="address">
            <p class="address-text">2023년 11월 12일 일요일 오전 11시</p>
            <p class="address-text">라뷰웨딩컨벤션 4층 라빌리에 홀</p>
        </div>
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
    position: relative;
    z-index: 1;
}
.img {
    width: 100%;
    margin-top: 20vw;
}
.address {
    margin: auto;
    margin-top: 20vw;
    margin-bottom: 20vw;
}
.address-text {
    font-size: 1rem;
}

</style>