<template>
    <div class="map">
        <div id="mapdata"></div>
        <div class="address">
            <span class="address-title">주소:</span> <span class="address-text">경북 구미시 새마을로 225</span> <button @click="copyAddress"></button>
        </div>
        <div class="transinfo">
            <p class="transinfo-title">대중교통 이용 시</p>
            <p></p>
            <p class="transinfo-title">자가용 이용 시</p>
            <p></p>
        </div>
    </div>
</template>

<script>
import Vue from 'vue'
import VueClipboard from 'vue-clipboard2'

VueClipboard.config.autoSetContainer = true;
Vue.use(VueClipboard)

export default {
    name: 'Map',
    props: {
        
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
                center: new window.naver.maps.LatLng(36.1031018, 128.3615057),
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
                    alert("주소를 클립보드에 복사하였습니다.")
            })
        }
    }       
}
</script>

<style scoped>
.map {
    width: 100%;
    margin: 0;
    align-items: center;
    margin-top: 20vw;
    margin-bottom: 20vw;
}
.img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
#mapdata {
    width: 90%; 
    height: 50vw;
    margin: auto;
}
.address {
    font-size: 2.5vw;
    margin-top: 10vw;
}
.address-title {
    font-size: 2.5vw;
    font-weight: bold;
}
.address-text {
    font-size: 2.5vw;
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
</style>