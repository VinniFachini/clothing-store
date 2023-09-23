<template>
    <Head>
        <Title>Products - Clothing Store Online</Title>
        <Meta name="description" content="An Online Clothing Store" />
    </Head>
    <div class="page-container">
        <aside>
            <div class="filter-container">
                <h3><mark>Filter</mark></h3>
                <ul class="filter-list">
                    <li v-for="category in categories" :key="category.id" class="filter-list__item">
                        <NuxtLink :to="{name: 'category-id', params: {id: category.slug}}" >{{ category.name }}</NuxtLink>                     
                    </li>
                </ul>
                <div v-for="attribute in attributes" :key="attribute.queryPrefix" class="filter-attributes">
                    <h3 class="filter-attributes__title">{{ attribute.filterName }}</h3>
                    <ul class="filter-attributes__list">
                        <li v-for="size in attribute.sizes" :key="size" class="filter-attributes__list__item">
                            <NuxtLink :to="{path: 'products'}" >{{ attribute.queryPrefix }}</NuxtLink>    
                        </li>    
                    </ul>
                </div>
            </div>
        </aside>
        <div class="mobile-backdrop"></div>
        <main>
            <div class="search-control">
                <button>Filter</button>
                <h2>Our Products</h2>
                <select name="orderby" id="orderby">
                    <option value="default">Order By</option>
                </select>
            </div>
            <div class="products-container">
                <ul class="products">
                    <Product
                        v-for="product in products"
                        :key="product.id"
                        :title="product.name"
                        :oldPrice="product.oldPrice"
                        :newPrice="product.newPrice"
                        :images="product.images"
                        :sku="product.sku"
                    />
                </ul>
            </div>
        </main>
    </div>
</template>

<style lang="scss" scoped>
    .page-container {
        main {
            margin-bottom: 80px;
        }
        display: grid;
        grid-template-columns: 350px 1fr;
        padding-right: 20px;
        background: #f1f1f1;
        .search-control {
            display: flex;
            align-content: center;
            justify-content: center;
            position: relative;
            margin-left: 20px;
            padding-block: 30px;
            button {
                display: none;
                position: absolute;
                left: 0px;
                top: 50%;
                transform: translateY(-50%);
            }
            select {
                position: absolute;
                right: 0;
                top: 50%;
                transform: translateY(-50%);
            }
            h2 {
                font-size: 2.5rem;
                font-weight: 500;
            }
        }
        .products-container {
            margin-left: 20px;
            ul {
                display: grid;
                grid-template-columns: repeat(4, 1fr);
                gap: 20px;
            }
        }
        aside {
            background: #fff;
            position: relative;
            .filter-container {
                padding: 20px 20px;
                > h3 {
                    border-bottom: 1px solid #222;
                    padding-bottom: 8px;
                    padding-top: 20px;
                    mark {
                        background-color: transparent;
                        padding-left: 16px;
                        font-size: 1.8rem;
                    }
                }   
                .filter-list {
                    display: flex;
                    align-items: center;
                    justify-content: flex-start;
                    column-gap: 10px;
                    flex-wrap: wrap;
                    &__item {
                        width: fit-content;
                        a {
                            font-size: 1.2rem;
                            &:hover {
                                text-decoration: underline #222;
                                text-underline-offset: 4px
                            }
                        }
                    }
                }
            }
        }
        .mobile-backdrop {
            display: none;
        }
    }

    @media screen and (max-width: 992px) {
        .page-container {
            grid-template-columns: 1fr;
            aside {
                visibility: hidden;
                opacity: 0;
                height: 100vh;
                width: 80vw;
                position: fixed;
                top: 0;
                left: 0;
                z-index: 999;
                transform: translateX(-110%);
                transition: all .2s linear;
                &.active {
                    transform: translateX(0);
                    opacity: 1;
                    visibility: visible;
                }
            }
            .mobile-backdrop {
                z-index: 998;
                width: 100vw;
                position: fixed;
                top: 0;
                left: 0;
                height: 100vh;
                background-color: rgba(0,0,0,0.4);
                visibility: hidden;
                opacity: 0;
                display: block;
                &.active {
                    opacity: 1;
                    visibility: visible;
                }
            }
        }
    }
    
</style>

<script>
export default {
    data() {
        return {
            products: [],
            attributes: [],
            categories: []
        }
    },
    mounted() {
        this.fetchProducts("../api.json");
        this.fetchAttributes("../api.json");
        this.fetchCategories("../api.json");
    },
    methods: {
        fetchProducts: async function (url) {
            const info = await fetch(url);
            const infoJson = await info.json();
            this.products = infoJson.products;
        },
        fetchAttributes: async function (url) {
            const info = await fetch(url);
            const infoJson = await info.json();
            this.attributes = infoJson.attributes;
        },
        fetchCategories: async function (url) {
            const info = await fetch(url);
            const infoJson = await info.json();
            this.categories = infoJson.categories;
        }
    }
}
</script>   
