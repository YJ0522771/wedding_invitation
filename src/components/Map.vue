<template>
    <div class="map">
        <h3>Location</h3>
        <div id="mapdata"></div>
    </div>
</template>

<script>
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
                center: new window.naver.maps.LatLng(36.1031018, 128.3615047),
                zoom: 16
            });

            new window.naver.maps.Marker({
                position: new window.naver.maps.LatLng(36.1031018, 128.3615047),
                map: map
            });
        };
    }
            
}
</script>

<style scoped>
.map {
    width: 100%;
    margin: 0;
    align-items: center;
}
.img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
#mapdata {
    width:60%; 
    height:50vw;
    margin: auto;
}
</style>