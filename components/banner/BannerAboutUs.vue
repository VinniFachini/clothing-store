<template>
    <div class="banner-about-us container">
        <figure v-for="item in banners" :key="item.title">
            <img :src="item.link" alt="" srcset="">
        </figure>
    </div>
</template>

<script>
export default {
    props: {
        banners: Object,
        title: String,
    }
}
</script>

<style lang="scss" scoped>
.banner-about-us {
    display: grid;
    align-items: center;
    justify-content: center;
    grid-template-columns: repeat(4, 1fr);
    column-gap: 10px;
    margin-bottom: 40px;
    figure {
        width: 100%;
        height: 100%;
        &:first-of-type {
            grid-column: 1 / 3;
        }
        img {
            width: 100%;
            height: 100%;
            max-height: 500px;
            object-fit: cover;
        }
    }
}
</style>