<template>
    <Head>
        <Title>Products - Clothing Store Online</Title>
        <Meta name="description" content="An Online Clothing Store" />
    </Head>
    <div class="page-container">
        <aside :class="{ active: mobileMenuActive }">
            <div class="filter-container">
                <h3><mark>Filter</mark></h3>
                <ul class="filter-list">
                    <li v-for="category in categories" :key="category.id" class="filter-list__item">
                        <NuxtLink :to="{name: 'category-id', params: {id: category.slug}}" >{{ category.name }}</NuxtLink>                     
                    </li>
                </ul>

                <div v-if="activeFilters" class="filter-active-list">
                    <h3><mark>Active Filters</mark></h3>
                    <ul class="filter-active-list">
                        <li class="filter-active-list__item" v-for="filter in activeFilters" :key="filter">
                            <span class="item-info">{{filter.filterName}}: <strong>{{ filter.value }}</strong></span>
                            <span @click="removeFilter(filter)" class="item-erase">x</span>
                        </li>
                    </ul>
                </div>

                <div v-for="attribute in attributes" :key="attribute.queryPrefix" class="filter-attributes">
                    <h3 class="filter-attributes__title">{{ attribute.filterName }}</h3>
                    <ul v-if="attribute.filterType == 'size'" class="filter-attributes--size__list">
                        <li v-for="size in attribute.sizes" :data-size-id="attribute.queryPrefix + size" :key="size" class="filter-attributes--size__list__item">
                            <span @click="activeFilter(attribute, size); activeMenuMobile(); loadSessionStorage()">{{ size }}</span> 
                        </li>    
                    </ul>
                    <ul v-if="attribute.filterType == 'color'" class="filter-attributes--color__list">
                        <li v-for="color in attribute.colors" :data-size-id="attribute.queryPrefix + color.colorName" :key="color.colorName" class="filter-attributes--color__list__item">
                            <span @click="activeFilter(attribute, color.colorName); activeMenuMobile(); loadSessionStorage()">
                                <div class="color-sample" :style="{'background-color': color.hex}"></div>
                                <span class="color-name">{{ color.colorName }}</span>
                            </span> 
                        </li>    
                    </ul>
                </div>
            </div>
        </aside>
        <div class="mobile-backdrop" :class="{ active: mobileMenuActive }" @click="activeMenuMobile"></div>
        <main>
            <div class="search-control">
                <button @click="activeMenuMobile">Filter</button>
                <h2>Our Products</h2>
                <div class="select">
                    <select v-model="order" @change="handleChange()" name="orderby" id="orderby">
                        <option value="default">Order By</option>
                        <option value="asc_name">Name A - Z</option>
                        <option value="desc_name">Name Z - A</option>
                        <option value="smallest_price">Smallest Price</option>
                        <option value="biggest_price">Biggest Price</option>
                        <option value="most_recent">Most Recent</option>
                        <option value="best_sellers">Best Sellers</option>
                    </select>
                </div>
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
                @media screen and (max-width: 992px) {
                    display: flex;
                    width: 100%;
                    max-width: 130px;
                    justify-content: center;
                    align-items: center;
                    background: #222;
                    color: white;
                    padding-block: 5px;
                    border: none;
                }
                @media screen and (max-width: 500px) {
                    max-width: unset !important;
                    position: relative !important;
                }
            }
            select {
                appearance: none;
                outline: 10px red;
                border: 0;
                box-shadow: none;
                min-width: 160px;
                width: 100%;
                flex: 1;
                padding: 0 1em;
                color: #fff;
                background-color: #222;
                background-image: none;
                cursor: pointer;
                padding-block: 5px;
                &::-ms-expand {
                   display: none;
                }
            }
            .select {
                position: absolute;
                right: 0;
                top: 50%;
                transform: translateY(-50%);
                display: flex;
                border-radius: .25em;
                overflow: hidden;
                &::after {
                content: '\25BC';
                position: absolute;
                top: 0;
                right: 0;
                padding: 0;
                background-color: #444;
                color: white    ;
                transition: .25s all ease;
                pointer-events: none;
                font-size: 12px;
                height: 100%;
                line-height: 2;
                aspect-ratio: 1/1;
                text-align: center;
                padding-block: 5px;
                }
                @media screen and (max-width: 500px) {
                    position: relative;
                    width: 100%;
                }
            }
            h2 {
                font-size: 2.5rem;
                font-weight: 500;
                @media screen and (max-width: 768px) {
                    font-size: 2rem;
                }
                @media screen and (max-width: 500px) {
                    font-size: 2rem;
                    width: 100%;
                    margin-bottom: 35px;
                }
            }
            @media screen and (max-width: 500px) {
                flex-direction: column;
            }
        }
        .products-container {
            margin-left: 20px;
            ul {
                display: grid;
                grid-template-columns: repeat(4, 1fr);
                gap: 20px;
                @media screen and (max-width: 1200px) {
                    grid-template-columns: repeat(3, 1fr);
                }
                @media screen and (max-width: 1024px) {
                    grid-template-columns: repeat(2, 1fr);
                }
                @media screen and (max-width: 992px) {
                    grid-template-columns: repeat(3, 1fr);
                }
                @media screen and (max-width: 768px) {
                    grid-template-columns: repeat(2, 1fr);
                }
                @media screen and (max-width: 425px) {
                    grid-template-columns: repeat(1, 1fr);
                }
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
                .filter-attributes{
                    &__title {
                        font-size: 1.2rem;
                        margin-block: 10px 5px;
                    }
                    &--size{
                        &__list {
                            width: 100%;
                            display: flex;
                            flex-direction: column;
                            align-items: flex-start;
                            justify-content: flex-start;
                            &__item {
                                width: 100%;
                                cursor: pointer;
                                span {
                                    width: 100%;
                                    display: inline-block;
                                    padding-left: 15px;
                                    padding-block: 5px;
                                }
                                &:hover {
                                    span {
                                        text-decoration: underline;
                                        text-underline-offset: 2px;
                                    }
                                }
                                &.disabled {
                                    cursor: not-allowed;
                                    pointer-events: none;
                                    opacity: 0.7;
                                }
                            }
                        }
                    }
                    &--color {
                        &__list {
                            width: 100%;
                            display: flex;
                            flex-direction: column;
                            align-items: flex-start;
                            justify-content: flex-start;
                            &__item {
                                width: 100%;
                                cursor: pointer;
                                span {
                                    width: 100%;
                                    padding-left: 15px;
                                    padding-block: 5px;
                                    display: flex;
                                    align-items: center;
                                    justify-content: flex-start;
                                    .color-sample {
                                        min-width: 20px;
                                        min-height: 20px;
                                    }
                                }
                                &:hover {
                                    span .color-name {
                                        text-decoration: underline;
                                        text-underline-offset: 2px;
                                    }
                                }
                                &.disabled {
                                    cursor: not-allowed;
                                    pointer-events: none;
                                    opacity: 0.7;
                                }
                            }
                        }
                    }
                }
                .filter-active-list{
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
                    ul {
                        display: flex;
                        flex-direction: column;
                        align-items: flex-start;
                        justify-content: center;
                    }
                    &__item {
                        width: 100%;
                        display: flex;
                        align-items: center;
                        justify-content: space-between;
                        padding-inline: 10px;
                        padding-block: 5px;
                        .item-info {
                            font-size: 1.2rem;
                            strong{
                                font-size: 1.2rem;
                            }
                        }
                        .item-erase {
                            text-indent: -999999999px;
                            width: 20px;
                            height: 20px;
                            background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjUiIHZpZXdCb3g9IjAgMCAyNCAyNSIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTE5IDYuNzk3MDhMMTcuNTkgNS4zODcwOEwxMiAxMC45NzcxTDYuNDEgNS4zODcwOEw1IDYuNzk3MDhMMTAuNTkgMTIuMzg3MUw1IDE3Ljk3NzFMNi40MSAxOS4zODcxTDEyIDEzLjc5NzFMMTcuNTkgMTkuMzg3MUwxOSAxNy45NzcxTDEzLjQxIDEyLjM4NzFMMTkgNi43OTcwOFoiIGZpbGw9IiMzMzMzMzMiLz4KPC9zdmc+Cg==) no-repeat center center;
                            cursor: pointer;
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
            categories: [],
            mobileMenuActive: false,
            activeFilters: null,
            order: 'default'
        }
    },
    mounted() {
        this.fetchProducts("../api.json");
        this.fetchAttributes("../api.json");
        this.fetchCategories("../api.json");
        this.loadSessionStorage()

    },
    // beforeUnmount() {
    //     sessionStorage.removeItem("selectedFilters")
    // },
    watch: {
        $route: {
            handler(to, from) {

                console.log("Route changed: ", to, from)
            },
            deep: true
        }
    },
    methods: {
        removeFilter: function(filter) {
            const items = JSON.parse(sessionStorage.getItem("selectedFilters"))
            const currentElement = document.querySelector(`li[data-size-id="${filter.filterPrefix}${filter.value}"]`)
            if(currentElement.classList.contains('disabled')) {
                currentElement.classList.remove('disabled')
            } else {
                currentElement.classList.add('disabled')
            }
            const newArr = items.map(item => !(item.filterName == filter.filterName && item.value == filter.value) ? item : '').filter(obj => obj)
            sessionStorage.setItem("selectedFilters", JSON.stringify(newArr))
            this.activeFilters = newArr
            const route = useRoute()
            const router = useRouter()

            const first = `?${filter.filterPrefix}=${filter.value}` 
            const whatever = `&${filter.filterPrefix}=${filter.value}`
            let newUrl;

            if (route.fullPath.includes(first)) {
                newUrl = route.fullPath.replace(first, '')
                if(newUrl.startsWith(`${route.path}&`)) {
                    newUrl = newUrl.replace(`${route.path}&`, `${route.path}?`)
                    router.replace(newUrl)
                }
            } else if (route.fullPath.includes(whatever)) {
                newUrl = route.fullPath.replace(whatever, '')
                if(newUrl.startsWith(`${route.path}&`)) {
                    newUrl = newUrl.replace(`${route.path}&`, `${route.path}?`)
                    router.replace(newUrl)
                } else {
                    router.replace(newUrl)
                }
            } 

            if(newUrl == `${route.path}`) {
                router.replace(newUrl)
            }

            if(this.activeFilters.length == 0) {
                this.activeFilters = null
            }
        },
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
        },
        activeFilter: function(attr, size) {
            const currentElement = document.querySelector(`li[data-size-id="${attr.queryPrefix}${size}"]`)
            if(currentElement.classList.contains('disabled')) {
                currentElement.classList.remove('disabled')
            } else {
                currentElement.classList.add('disabled')
            }
            const router = useRouter()
            const route = useRoute()
            let storage = sessionStorage.getItem("selectedFilters")

            if(Object.keys(route.query).length == 0 && route.query.constructor === Object) {
                router.push((`${route.path}?${attr.queryPrefix}=${size}`))
                if(storage){
                    let newSession = []
                    newSession = newSession.concat(JSON.parse(storage))
                    newSession.push({filterName: attr.filterName, value: size, filterPrefix: attr.queryPrefix})
                    sessionStorage.setItem("selectedFilters", JSON.stringify(newSession))
                } else {
                    let newSession = []
                    newSession.push({filterName: attr.filterName, value: size, filterPrefix: attr.queryPrefix})
                    sessionStorage.setItem("selectedFilters", JSON.stringify(newSession))
                }
            } else {
                const newSize = size
                const items = Object.values(route.query)[Object.keys(route.query).indexOf(attr.queryPrefix)] || []
                if(!items.includes(newSize)) {
                    router.push((`${route.fullPath}&${attr.queryPrefix}=${size}`))
                    if(storage){
                    let newSession = []
                    newSession = newSession.concat(JSON.parse(storage))
                    newSession.push({filterName: attr.filterName, value: size, filterPrefix: attr.queryPrefix})
                    sessionStorage.setItem("selectedFilters", JSON.stringify(newSession))
                    } else {
                        let newSession = []
                        newSession.push({filterName: attr.filterName, value: size, filterPrefix: attr.queryPrefix})
                        sessionStorage.setItem("selectedFilters", JSON.stringify(newSession))
                    }
                }
            } 
        },
        activeMenuMobile: function() {
            this.mobileMenuActive = !this.mobileMenuActive 
        },
        loadSessionStorage: function() {
            let storage = sessionStorage.getItem("selectedFilters")
            if(storage) {
                let getItems = Array.from(new Set(JSON.parse(sessionStorage.getItem("selectedFilters"))))
                this.activeFilters = getItems
            } else {
                sessionStorage.setItem("selectedFilters", [])
            }
        },
        handleChange: function() {
            const router = useRouter()
            const route = useRoute()

            if(this.order == "default") {
                let newQueryParams = {
                    ...route.query,
                    order: undefined,
                };
                router.replace({ query: newQueryParams })
            } else {
                if(!Object.entries(route.query).length) {
                    router.push(`?order=${this.order}`)
                } else {
                    if(Object.keys(route.query).includes("order")){
                        let newQueryParams = {
                            ...route.query,
                            order: this.order,
                        };
                        router.replace({ query: newQueryParams })
    
                    } else {
                        router.push(`${route.fullPath}&order=${this.order}`)
                    }
                }
            }

        }
    }
}
</script>   
