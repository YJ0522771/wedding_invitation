<template>
    <div  id="carouselExample" class="carousel slide gallery-carousel">
        <div class="carousel-inner">
            <div
            v-for="(file_name, idx) in picture_names"
            :key="idx" 
            :class="{'carousel-item': true, 'active': idx == picture_idx}">
                <img 
                :src="file_name" 
                class="img">
            </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev"
        @click="minusPictureNum">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next"
        @click="plusPictureNum">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
        <button type="button" class="btn-close" aria-label="Close"
        @click="closeCarousel"></button>
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
    --bs-modal-zindex: 10;
    z-index: var(--bs-modal-zindex);
    top: 0;
    left: 0;
    justify-content: center;
    background-color: #00000088;
    width: 100%;
    height: 100%;
}
.img {
    width: 80vw;
    height: 80vh;
    margin: auto;
    object-fit: contain;
    margin-top: 10vh;
}
.btn-close {
    width: 5vw;
    height: 5vw;
    margin-top: 2vh;
}
</style>