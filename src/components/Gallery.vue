<template>
    <div class="gallery">
        <div v-if="carouselVisible">
            <GalleryCarousel 
            :p_idx="clicked_idx"
            @close="nonVisibleCarousel"
            />
        </div>
        <h3>Gallery</h3>
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

export default {
    name: 'Gallery',
    props: {
    
    },
    components: {
        GalleryCarousel,
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
            // console.log(this.carouselVisible)
        },
        nonVisibleCarousel: function () {
            this.carouselVisible = false;
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
}
.row {
    --bs-gutter-x: 1vw;
    --bs-gutter-y: 0;
    display: flex;
    flex-wrap: wrap;
    margin-top: calc(-1 * var(--bs-gutter-y));
    align-items: center;
    justify-content: center;
}
.col {
    flex: 0 0 0%;
    margin: 1vw;
    align-items: center;
}
.img {
    width: 40vw;
    height: 40vw;
    object-fit: cover;
    display: flex;
    position: relative;
    margin: auto;
}

</style>