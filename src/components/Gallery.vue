<template>
    <div class="gallery">
        <div v-if="carouselVisible">
            <GalleryCarousel 
            :p_idx="clicked_idx"
            @close="nonVisibleCarousel"
            />
        </div>
        <Headline
        headline="갤러리" />
        <div class="row">
            <div class="col"
            v-for="(file_name, idx) in picture_names"
            :key="file_name">
                <img class="img"
                :src="file_name"
                @click="visibleCarousel(idx)">
            </div>
        </div>
        
    </div>
</template>

<script>
import GalleryCarousel from './GalleryCarousel.vue'
import Headline from './Headline.vue'

export default {
    name: 'Gallery',
    props: {
    
    },
    components: {
        GalleryCarousel,
        Headline
    },
    data: function() {
        return {
            picture_names: [
                require('@/assets/pictures/01.jpg'),
                require('@/assets/pictures/02.jpg'),
                require('@/assets/pictures/03.jpg'),
                require('@/assets/pictures/04.jpg'),
                require('@/assets/pictures/05.jpg'),
                require('@/assets/pictures/06.jpg'),
                require('@/assets/pictures/07.jpg'),
                require('@/assets/pictures/08.jpg'),
                require('@/assets/pictures/09.jpg'),
                require('@/assets/pictures/10.jpg'),
                require('@/assets/pictures/11.jpg'),
                require('@/assets/pictures/12.jpg'),
                require('@/assets/pictures/13.jpg'),
                require('@/assets/pictures/14.jpg'),
                require('@/assets/pictures/15.jpg')
            ],
            clicked_idx: 0,
            carouselVisible: false,
        }
    },
    methods: {
        visibleCarousel: function (idx) {
            this.clicked_idx = idx;
            // console.log(this.clicked_idx)
            this.carouselVisible = true;
            let ele = document.querySelector('body');
            ele.style.overflow = 'hidden';
            // console.log(this.carouselVisible)
        },
        nonVisibleCarousel: function () {
            this.carouselVisible = false;
            let ele = document.querySelector('body');
            ele.style.overflow = 'scroll';
            console.log("close carousel")
        }
    },
}
</script>

<style scoped>
.gallery {
    width: 100%;
    align-items: center;
    justify-content: center;
    z-index: 2;
    position: relative;
    margin: 50vw 0;
}
.row {
    --bs-gutter-x: 1vw;
    --bs-gutter-y: 0;
    display: flex;
    flex-wrap: wrap;
    margin-top: calc(-1 * var(--bs-gutter-y));
    margin-right: 0;
    margin-left: 0;
    align-items: center;
    justify-content: center;
}
.col {
    flex: 0 0 0%;
    margin: 1vw;
    align-items: center;
}
.img {
    width: 28vw;
    height: 28vw;
    object-fit: cover;
    display: flex;
    position: relative;
    margin: auto;
}

</style>