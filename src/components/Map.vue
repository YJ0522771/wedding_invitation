<template>
    <div class="map">
        <Headline
        headline="예식장 안내"/>
        <div id="mapdata"></div>
        <div class="address">
            <span class="address-title">주소 : </span> 
            <span class="address-text">경북 구미시 새마을로 225</span> <button class="btn" @click="copyAddress"><i class="fas fa-copy"></i></button>
        </div>
        <div>
            <a href="https://surl.tmobiapi.com/84c21001">
                <img src="@/assets/icons/Tmap.png"
                class="icon"/>
            </a>
            <a href="https://naver.me/G6DymFD8">
                <img src="@/assets/icons/Naver.png"
                class="icon"/>
            </a>
            <a href="https://kko.to/LIR5wXn5Wr">
                <img src="@/assets/icons/Kakao.png"
                class="icon"/>
            </a>
        </div>
    </div>
</template>

<script>
import Vue from 'vue'
import VueClipboard from 'vue-clipboard2'
import Headline from './Headline.vue'

VueClipboard.config.autoSetContainer = true;
Vue.use(VueClipboard)

export default {
    name: 'Map',
    props: {
        
    },
    components: {
        Headline,
    },
    mounted() {
        // 네이버 지도 API 로드
        const script = document.createElement("script");
        script.src ="https://openapi.map.naver.com/openapi/v3/maps.js?ncpClientId=e4wohmvzn4";
        script.async = true;
        script.defer = true;
        document.head.appendChild(script);

        script.onload = () => {
        // 네이버 지도 생성
            var map = new window.naver.maps.Map("mapdata", {
                center: new window.naver.maps.LatLng(36.102497, 128.362889),
                draggable: false,
                disableDoubleTapZoom: true,
                disableTwoFingerTapZoom: true,
                zoomControl: true,
                zoom: 16
            });

            new window.naver.maps.Marker({
                position: new window.naver.maps.LatLng(36.1031018, 128.3615047),
                map: map
            });
        };
    },
    methods: {
        copyAddress: function () {
            this.$copyText("경북 구미시 새마을로 225").then(()=> {
                alert("복사 완료.");
            })
        }
    }       
}
</script>

<style scoped>
.map {
    width: 100%;
    margin: 50vw 0;
    align-items: center;
    z-index: 1;
    position: relative;
}
.img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
#mapdata {
    width: 90%; 
    height: 70vw;
    margin: auto;
}
.address {
    margin-top: 10vw;
    align-content: center;
    text-align: center;
    font-family: 'Poor Story', cursive;
}
.address-title {
    font-size: 1rem;
    font-weight: bold;
}
.address-text {
    font-size: 1rem;
    
}
.transinfo {
    margin: 10vw 10vw 20vw 20vw;
    text-align: start;
}
.transinfo-title {
    color: #004f08;
    font-weight: bold;
    font-size: 2.5vw;
}
.icon {
    width: 10vw;
    height: 10vw;
    margin: 3vw;
}
.btn {
    padding: 0;
    width: 7vw;
    height: 7vw;
}
.copy  {
    width: 4vw;
    height: 4vw;
    margin: 0;
}
</style>