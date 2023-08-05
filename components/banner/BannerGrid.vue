<template>
    <div class="container banner-grid-wrapper">
        <img class="first-image" :src="first" :alt="title">
        <img class="second-image" :src="second" :alt="title">
        <img class="third-image" :src="third" :alt="title">
    </div>
</template>

<script>
export default {
    props: {
        first: String,
        second: String,
        third: String,
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
    .first-image {
        grid-column: 1 / 3;
        grid-row: 1 / 3;
        width: 100%;
        height: 100%;
    }
    .second-image, .third-image {
        grid-column: 3 / 5;
    }
}
</style>