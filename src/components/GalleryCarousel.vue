<template>
    <div  id="carouselExample" class="carousel slide gallery-carousel">
        <!-- <button type="button" class="btn-close" aria-label="Close"
        @click="closeCarousel"></button> -->
        <div class="carousel-inner">
            <div
            v-for="(file_name, idx) in picture_names"
            :key="idx" 
            :class="{'carousel-item': true, 'active': idx == picture_idx}">
                <div class="space" @click="closeCarousel"></div>
                <img 
                :src="file_name" 
                class="img">
                <p class="number">{{ idx + 1 }} / {{ picture_names.length }}</p>
                <div class="space" @click="closeCarousel"></div>
            </div>
        </div>
        <button class="carousel-control-prev"
        @click="minusPictureNum">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next"
        @click="plusPictureNum">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
    </div>
</template>

<script>
export default {
    name: 'GalleryCarousel',
    props: {
        p_idx: Number
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
            picture_idx: this.p_idx,
        }
    },
    methods: {
        plusPictureNum: function () {
            this.picture_idx++;
            if (this.picture_idx >= 15)
            {
                this.picture_idx = 0;
            }
            console.log(this.picture_idx)
        },
        minusPictureNum: function () {
            this.picture_idx--;
            if (this.picture_idx < 0)
            {
                this.picture_idx = 14;
            }
            console.log(this.picture_idx)
        },
        closeCarousel: function () {
            this.$emit('close')
        }
    },
}
</script>

<style scoped>
.gallery-carousel {
    position: fixed;
    margin: 0;
    --bs-modal-zindex: 100;
    z-index: var(--bs-modal-zindex);
    top: 0;
    left: 0;
    justify-content: center;
    background-color: #00000088;
    width: 100%;
    height: 100%;
}
.carousel-item {
    height: 100%;
}
.img {
    width: 80vw;
    height: calc(min(80vh, 120vw));
    margin: auto;
    object-fit: contain;
    z-index: 10;
}
.space {
    height: calc((100vh - min(80vh, 120vw))/2);
    margin: auto;
}
.number {
    color: rgb(44, 44, 44);
    margin: 1vw
}
.btn-close {
    width: 5vw;
    height: 5vw;
    margin-top: 5%;
    margin-left: 80%;
}
.carousel-control-prev {
    height: 40%;
    margin: auto
}
.carousel-control-next {
    height: 40%;
    margin: auto
}
</style>