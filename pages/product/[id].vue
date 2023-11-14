<template>
    <div class="container">
        {{ productInfo }}
    </div>
</template>

<script>
export default {
    data(){
        return {
            productInfo: []
        }
    },
    mounted() {
        this.fetchProductInfo("../api.json")
    },
    methods: {
        fetchProductInfo: async function (url) {
            const info = await fetch(url);
            const infoJson = await info.json();
            console.log(infoJson.products)
            infoJson.products.map(product => {
                if (product.sku == this.$route.params.id) {
                    this.productInfo = product
                }
            })
        },
    }
} 
</script>

<style>
</style>