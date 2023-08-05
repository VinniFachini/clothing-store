<template>
  <li class="product-item">
    <figure>
        <NuxtLink :to="productLink"> 
            <img :src="images.main" :alt="title" />
            <img class="hover-img" :src="images.thumbs[0]" :alt="title" />
        </NuxtLink>
    </figure>
    <figcaption>
        {{ title }}
    </figcaption>
    <div class="price">
        <div class="old-price">
            <span class="old-price__value">{{ oldPriceFormated }}</span>
        </div>
        <div class="new-price">
            <span class="new-price__value">{{ newPriceFormated }}</span>
        </div>
    </div>
  </li>
</template>

<style lang="scss" scoped>
.product-item {
    width: 100%;
    margin-inline: 5px;
    figure {
        width: 100%;
        img {
            width: 100%;
            aspect-ratio: 2 / 3;
            object-fit: cover;
            opacity: 1;
            visibility: visible;
            display: block;
            &.hover-img{
                display: none;
                visibility: hidden;
                opacity: 0;
            }
        }
    }
    figcaption {
        font-size: 1.3rem;
    }
    .old-price{
        &__value {
            font-size: 1rem;
            text-decoration: line-through;
            color: #939393;
        }
    }
    .new-price {
        &__value {
            font-size: 1.3rem;
            color: #111;
        }
    }
}
</style>

<script>
export default {
  setup() {},
  data(){
    return {
        productLink: `/product/${this.sku}`
    }
  },
  props: {
    title: String,
    oldPrice: String,
    newPrice: String,
    images: String,
    sku: String
  },
  computed: {
    oldPriceFormated: function () {
      return `$${Number.parseFloat(this.oldPrice).toFixed(2)}`;
    },
    newPriceFormated: function () {
      return `$${Number.parseFloat(this.newPrice).toFixed(2)}`;
    },
  },
};
</script>