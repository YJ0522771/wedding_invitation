<template>
    <div id="app">
        <!-- 브라우저 화면 크기 : <span>{{ windowWidth }}</span> * <span>{{ windowHeight }}</span> <span>"Is moblie: {{ isMobile }}"</span> -->
        
        <Title/>
        <Invitation/>
        <Information/>
        <Gallery/>
        <Map/>
        <Contact/>
        <Footer/>
        <img src="@/assets/contents/bg.png" class="bg"/>
    </div>
</template>

<script>
import Title from './components/Title.vue'
import Invitation from './components/Invitation.vue'
import Information from './components/Information.vue'
import Gallery from './components/Gallery.vue'
import Map from './components/Map.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

export default {
    name: 'App',
    components: {
        Title,
        Invitation,
        Information,
        Gallery,
        Map,
        Contact,
        Footer
    },
    data: function() {
        return {
            windowWidth: window.innerWidth,
            windowHeight: window.innerHeight
        }
    },
    created() {
        
        window.history.pushState({id: 1, data: 'main'}, '이준우&조유진 결혼합니다', "https://m.site.naver.com/1cTAb");
    },
    mounted() {
       // console.log(window.location.href);

        window.addEventListener('resize', () => {
            this.windowWidth = window.innerWidth
            this.windowHeight = window.innerHeight
            //console.log(this.isMobile)
        })
    },
    computed: {
        isMobile() {
            return this.windowWidth <= 768
        }
    }
}
</script>

<style>
#app {
    /* font-family: Avenir, Helvetica, Arial, sans-serif; */
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #050505;
    margin: 0;
    width: 100%;
    background: #fafafa;
    z-index: 1;
    position: relative;
}
.bg {
    width: 80%;
    position: fixed;
    top: 35vw;
    left: 0;
    margin: 0 10%;
    z-index: 0;
    opacity: 0.2;
}
</style>
