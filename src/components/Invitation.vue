<template>
    <div class="invitation">
        <div class="greeting">
            <!-- <p class="title-text">모시는 글</p>
            <br> -->
            <p class="text">13년을 변함없이 곁에 있었고</p>
            <p class="text">여기까지 올 수 있었습니다.</p>
            <p class="text">더 긴 세월을 함께하고자 결심하였으니</p>
            <p class="text">앞으로도</p>
            <p class="text">그저 지금처럼만 행복하길</p>
            <p class="text">한 마음으로 기도해주시면 감사하겠습니다.</p>
        </div>
        <div class="greeting">
            <div class="names">
                <span class="name-text">이기영 · 이화연</span>
                <span>의 장남</span>
                <span class="name-text">준우</span>
            </div>
            <div class="names">
                <span class="name-text">조재천 · 이길남</span>
                <span>의 장녀</span>
                <span class="name-text">유진</span>
            </div>
        </div>    
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
.greeting {
    width: 70%;
    margin: auto;
    margin-top: 30vw;
    margin-bottom: 30vw;
}
.title-text {
    font-size: 2.3vw;
}
.text {
    font-size: 4vw;   
}
.names {
    margin: 5vw
}
.name-text {
    font-size: 4vw;  
    font-weight: bolder;
    margin: 6vw
}
.other-text {
    font-size: 2vw; 
}
.img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
</style>