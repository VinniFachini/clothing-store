<template>
  <div class="container">
    <div class="photo-area">
      <figure v-for="image in productImages" :key="image" class="image-figure">
        <img :src="image" alt="" />
      </figure>
    </div>
    <div class="info-area">
      <h1 class="info-area__product-name">{{ productName }}</h1>
      <div class="info-area__productOverall">
        <div
          v-for="review in productStars"
          :key="review"
          class="stars-container"
        >
          <i class="star-full" v-if="review"></i>
          <i class="star-default" v-else></i>
        </div>
        <div class="review-number">{{ reviewsNumber }}</div>
      </div>
      <div class="info-area__product-price">
        <div class="info-area__product-price__old-price">
          ${{ productOldPrice }}
        </div>
        <div class="info-area__product-price__new-price">
          ${{ productNewPrice }}
          <span class="in-cash-label">
            in cash ({{ discountPercentage }}% OFF)
          </span>
        </div>
      </div>
      <div class="info-area__attributes">
        <div class="info-area__attributes-color">
          <span class="attribute-title">Colors:</span>
          <div class="attributes">
            <div
              v-for="color in productColors"
              :key="color.colorName"
              class="attribute-container"
            >
              <input
                type="hidden"
                :id="color.colorName"
                :name="color.colorName"
              />
              <label
                :for="color.colorName"
                @click="selectColor"
                :style="getColorStyle(color.hex)"
              ></label>
            </div>
          </div>
        </div>
        <div class="info-area__attributes-sizes">
          <span class="attribute-title">Sizes:</span>
          <div class="attributes">
            <div
              v-for="size in productSizes"
              :key="size"
              class="attribute-container"
            >
              <input type="hidden" :id="size" :name="size" />
              <label :for="size" @click="selectSize">{{ size }}</label>
            </div>
          </div>
        </div>
        <!-- <div class="info-area__attributes-sizes"> {{ productSizes }} </div> -->
      </div>
      <div class="info-area__buy-now">
        <button>Buy Now!</button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  display: grid;
  grid-template-columns: 2fr 1fr;
  margin-top: 60px;
}

.info-area {
  &__buy-now {
    margin-block: 40px;
    button {
      width: 100%;
      padding: 16px;
      border: none;
      background-color: #07623c;
      color: white;
      cursor: pointer;
      transition: all 0.2s linear;
      font-size: 20px;
      font-weight: 600;
      &:hover {
        background-color: #0b9b5f;
      }
    }
  }

  &__attributes {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    width: 100%;
    row-gap: 20px;
    &-color {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      width: 100%;
      .attribute-title {
        font-size: 1.2rem;
        width: 100%;
      }
      .attributes {
        display: flex;
        align-items: center;
        justify-content: flex-start;
        width: 100%;
        margin-top: 8px;
        gap: 16px;
        .attribute-container {
          label {
            width: 40px;
            height: 40px;
            display: block;
            cursor: pointer;
            transition: all 0.2s linear;
            position: relative;
            &.active {
              border: 5px solid #555555;
            }
          }
        }
      }
    }
    &-sizes {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      width: 100%;
      .attribute-title {
        font-size: 1.2rem;
        width: 100%;
      }
      .attributes {
        display: flex;
        align-items: center;
        justify-content: flex-start;
        width: 100%;
        margin-top: 8px;
        gap: 16px;
        .attribute-container {
          label {
            width: 40px;
            height: 40px;
            display: block;
            cursor: pointer;
            transition: all 0.2s linear;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 1px solid #000000;
            &.active {
              background-color: #000;
              color: white;
            }
          }
        }
      }
    }
  }
  padding-left: 20px;
  &__product-name {
    font-size: 2rem;
    font-weight: 600;
  }
  &__productOverall {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    .stars-container {
      width: 24px;
      height: 24px;
      i {
        width: 24px;
        height: 24px;
        display: inline-block;
        position: relative;
        &.star-full {
          background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzE0OV84KSI+CjxwYXRoIGQ9Ik0xMS40Nzk5IDMuNjA4OTZDMTEuNTY2NCAzLjM5Nzk1IDExLjc3MTkgMy4yNjAxMyAxMS45OTk5IDMuMjYwMTNDMTIuMjI4IDMuMjYwMTMgMTIuNDMzNCAzLjM5Nzk1IDEyLjUxOTkgMy42MDg5NkwxNC42NDQ5IDguNzE5OTZDMTQuNzI2IDguOTE0OTQgMTQuOTA5NCA5LjA0ODE0IDE1LjExOTkgOS4wNjQ5NkwyMC42Mzc5IDkuNTA2OTZDMjEuMTM2OSA5LjU0Njk2IDIxLjMzODkgMTAuMTcgMjAuOTU4OSAxMC40OTVMMTYuNzU0OSAxNC4wOTdDMTYuNTk0OCAxNC4yMzM5IDE2LjUyNDYgMTQuNDQ4OSAxNi41NzI5IDE0LjY1NEwxNy44NTc5IDIwLjAzOUMxNy45MTA4IDIwLjI1OTkgMTcuODI1NCAyMC40OTA5IDE3LjY0MTYgMjAuNjI0NEMxNy40NTc4IDIwLjc1NzggMTcuMjExNyAyMC43Njc1IDE3LjAxNzkgMjAuNjQ5TDEyLjI5MjkgMTcuNzY0QzEyLjExMzEgMTcuNjU0MSAxMS44ODY4IDE3LjY1NDEgMTEuNzA2OSAxNy43NjRMNi45ODE5NCAyMC42NUM2Ljc4ODIgMjAuNzY4NSA2LjU0MjEyIDIwLjc1ODggNi4zNTgzMSAyMC42MjU0QzYuMTc0NTEgMjAuNDkxOSA2LjA4OTEzIDIwLjI2MDkgNi4xNDE5NCAyMC4wNEw3LjQyNjk0IDE0LjY1NEM3LjQ3NTUzIDE0LjQ0ODggNy40MDUyNiAxNC4yMzM4IDcuMjQ0OTQgMTQuMDk3TDMuMDQwOTQgMTAuNDk1QzIuODY3ODEgMTAuMzQ3NCAyLjgwMDc0IDEwLjExIDIuODcxMDMgOS44OTM2MUMyLjk0MTMzIDkuNjc3MjQgMy4xMzUxMyA5LjUyNDYgMy4zNjE5NCA5LjUwNjk2TDguODc5OTQgOS4wNjQ5NkM5LjA5MDQ1IDkuMDQ4MTQgOS4yNzM4NCA4LjkxNDk0IDkuMzU0OTQgOC43MTk5NkwxMS40Nzk5IDMuNjA4OTZaIiBmaWxsPSJibGFjayIgc3Ryb2tlPSJibGFjayIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMTQ5XzgiPgo8cmVjdCB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIGZpbGw9IndoaXRlIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==)
            no-repeat;
        }
        &.star-default {
          background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzE0OV8yKSI+CjxwYXRoIGQ9Ik0xMS40Nzk5IDMuNjA4OTZDMTEuNTY2NCAzLjM5Nzk1IDExLjc3MTkgMy4yNjAxMyAxMS45OTk5IDMuMjYwMTNDMTIuMjI4IDMuMjYwMTMgMTIuNDMzNCAzLjM5Nzk1IDEyLjUxOTkgMy42MDg5NkwxNC42NDQ5IDguNzE5OTZDMTQuNzI2IDguOTE0OTQgMTQuOTA5NCA5LjA0ODE0IDE1LjExOTkgOS4wNjQ5NkwyMC42Mzc5IDkuNTA2OTZDMjEuMTM2OSA5LjU0Njk2IDIxLjMzODkgMTAuMTcgMjAuOTU4OSAxMC40OTVMMTYuNzU0OSAxNC4wOTdDMTYuNTk0OCAxNC4yMzM5IDE2LjUyNDYgMTQuNDQ4OSAxNi41NzI5IDE0LjY1NEwxNy44NTc5IDIwLjAzOUMxNy45MTA4IDIwLjI1OTkgMTcuODI1NCAyMC40OTA5IDE3LjY0MTYgMjAuNjI0NEMxNy40NTc4IDIwLjc1NzggMTcuMjExNyAyMC43Njc1IDE3LjAxNzkgMjAuNjQ5TDEyLjI5MjkgMTcuNzY0QzEyLjExMzEgMTcuNjU0MSAxMS44ODY4IDE3LjY1NDEgMTEuNzA2OSAxNy43NjRMNi45ODE5NCAyMC42NUM2Ljc4ODIgMjAuNzY4NSA2LjU0MjEyIDIwLjc1ODggNi4zNTgzMSAyMC42MjU0QzYuMTc0NTEgMjAuNDkxOSA2LjA4OTEzIDIwLjI2MDkgNi4xNDE5NCAyMC4wNEw3LjQyNjk0IDE0LjY1NEM3LjQ3NTUzIDE0LjQ0ODggNy40MDUyNiAxNC4yMzM4IDcuMjQ0OTQgMTQuMDk3TDMuMDQwOTQgMTAuNDk1QzIuODY3ODEgMTAuMzQ3NCAyLjgwMDc0IDEwLjExIDIuODcxMDMgOS44OTM2MUMyLjk0MTMzIDkuNjc3MjQgMy4xMzUxMyA5LjUyNDYgMy4zNjE5NCA5LjUwNjk2TDguODc5OTQgOS4wNjQ5NkM5LjA5MDQ1IDkuMDQ4MTQgOS4yNzM4NCA4LjkxNDk0IDkuMzU0OTQgOC43MTk5NkwxMS40Nzk5IDMuNjA4OTZaIiBzdHJva2U9ImJsYWNrIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz4KPC9nPgo8ZGVmcz4KPGNsaXBQYXRoIGlkPSJjbGlwMF8xNDlfMiI+CjxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiLz4KPC9jbGlwUGF0aD4KPC9kZWZzPgo8L3N2Zz4K)
            no-repeat;
        }
      }
    }
    .review-number {
      margin-left: 8px;
    }
  }
  &__product-price {
    line-height: 200%;
    margin-block: 40px;
    &__old-price {
      color: #989898;
      font-size: 1.5rem;
      text-decoration: line-through;
    }
    &__new-price {
      color: #000000;
      font-size: 2.5rem;
      display: flex;
      align-items: center;
      font-weight: 700;
      justify-content: flex-start;
      gap: 8px;
      .in-cash-label {
        font-weight: 400;
      }
    }
  }
}

.photo-area {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  .image-figure {
    img {
      width: 100%;
      height: 100%;
      aspect-ratio: 2/3;
    }
  }
}
</style>

<script>
export default {
  data() {
    return {
      productName: "",
      productImages: [],
      productSku: "",
      productMaterial: "",
      productDescription: "",
      productOldPrice: "",
      productNewPrice: "",
      productBrand: "",
      productId: "",
      productSizes: [],
      productColors: [],
      productReviews: [],
      productStars: [],
      reviewsNumber: "",
      discountPercentage: 0,
    };
  },
  async mounted() {
    await this.fetchProductInfo("../api.json");
    this.getAllStars();
    this.getReviewNumber();
    this.calculateDiscountPercentage();
  },
  methods: {
    selectColor(event) {
      const eita = document.querySelectorAll(
        ".info-area__attributes-color .attribute-container label"
      );
      eita.forEach((element) => {
        element.classList.remove("active");
      });
      event.srcElement.classList.toggle("active");
    },
    selectSize(event) {
      const eita = document.querySelectorAll(
        ".info-area__attributes-sizes .attribute-container label"
      );
      eita.forEach((element) => {
        element.classList.remove("active");
      });
      event.srcElement.classList.toggle("active");
    },
    getColorStyle(color) {
      return `background-color: ${color}`;
    },
    getAllStars() {
      const maxStars = 5;
      const newObj = {};

      for (let i = 0; i < maxStars; i++) {
        if (this.productReviews) {
          newObj[`${i + 1}`] =
            i < this.productReviews.productStarsOverall ? true : false;
        } else {
            newObj[`${i + 1}`] =
            i < 0 ? true : false;
        }
      }
      this.productStars = newObj;
    },
    getReviewNumber() {
      if (this.productReviews) {
        if (this.productReviews.reviews.length >= 1) {
          this.reviewsNumber = `${this.productReviews.reviews.length} Reviews`;
        }
      } else {
        this.reviewsNumber = `Review this Item`;
      }
    },
    calculateDiscountPercentage() {
      this.discountPercentage = (
        ((this.productOldPrice - this.productNewPrice) / this.productOldPrice) *
        100
      ).toFixed(0);
    },
    fetchProductInfo: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      infoJson.products.map((product) => {
        if (product.sku == this.$route.params.id) {
          this.productName = product.name;
          this.productImages = [
            product.images.main,
            product.images.mouseOver,
            ...product.images.thumbs,
          ];
          this.productSku = product.sku;
          this.productMaterial = product.material;
          this.productDescription = product.description;
          this.productOldPrice = product.oldPrice;
          this.productNewPrice = product.newPrice;
          this.productBrand = product.brand;
          this.productId = product.id;
          this.productSizes = product.attributes.size;
          this.productColors = product.attributes.color;
          this.productReviews = product.reviews;
        }
      });
    },
  },
};
</script>

<style>
</style>