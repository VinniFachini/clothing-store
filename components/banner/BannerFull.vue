<template>
    <section class="banner-full-container">
        <div class="container title-container">
            <h3 class="title">{{ title }}</h3>
        </div>
        <div class="container images">
            <figure v-for="item in banners" :key="item.bannerTitle">
                <img :src="item.link" alt="">
            </figure>
        </div>
    </section>
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
.banner-full-container {
    background-color: #f5f7fa;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    margin-bottom: 30px;
}
.title-container {
    .title {
        font-size: 20px;
        padding-block: 30px;
        font-weight: 600;
    }
}
.images {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    padding-bottom: 30px;
    figure {
        width: 100%;
        img {
            width: 100%;
        }
    }
}
</style>