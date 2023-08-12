<template>
    <div class="container banner-grid-wrapper">
        <figure v-for="item in banners" :key="item.title">
            <img :src="item.link" :alt="item.title">
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
.banner-grid-wrapper {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    padding-block: 40px;
    figure {
        grid-column: 3 / 5;
        width: 100%;
        img {
            width: 100% !important;
            height: 100% !important;
        }
        &:first-child {
            grid-column: 1 / 3 !important;
            grid-row: 1 / 3;
            width: 100%;
            height: 100%;
        }
    }
    @media screen and (max-width: 992px) {
        display: flex !important;
        flex-direction: column;
    }
}
</style>