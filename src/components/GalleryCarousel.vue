<template>
    <div class="gallery-carousel">
        
    </div>
</template>

<script>
export default {
    name: 'GalleryCarousel',
    props: {
        
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
        }
    }
}
</script>

<style scoped>
.gallery-carousel {
    width: 100%;
}

</style>