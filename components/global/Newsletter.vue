<template>
  <section class="newsletter container">
    <h3 class="newsletter__title">
      <span>Get $20 OFF</span>in your first purchase!
    </h3>
    <span class="newsletter__subtitle">Valid for purchases above $100</span>
    <form @submit.prevent="submitNewsletter" method="POST">
      <input
        class="input-text"
        type="text"
        name="email"
        id="email"
        placeholder="Type your e-mail"
        :value="email"
        @input="email = $event.target.value"
      />
      <input
        class="input-submit"
        type="submit"
        name="email"
        value="I WANT MY COUPON"
        id="email"
      />
    </form>
    <span class="newsletter__description"
      >We respect your privacy, we only send e-mails about our products</span
    >
    <div
      class="newsletter__success--backdrop"
      @click="toggleNewsletter"
      :class="{ active: isActive }"
    ></div>
    <div class="newsletter__success" :class="{ active: isActive }">
      <span class="close-icon" @click="toggleNewsletter"></span>
      <h3>You Got It!</h3>
      <span>$20 OFF at your first purchase</span>
      <input
        ref="coupon"
        v-model="coupon"
        type="text"
        name="coupon"
        id="coupon"
        readonly
      />
      <button @click="copyToClipboard">copy coupon</button>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      isActive: false,
      coupon: "FIRSTPURCHASE",
    };
  },
  methods: {
    submitNewsletter: function () {
      this.toggleNewsletter()
    },
    toggleNewsletter: function () {
      this.isActive = !this.isActive;
    },
    copyToClipboard: async function () {
      await navigator.clipboard.writeText(this.coupon);
      this.toggleNewsletter();
    },
  },
};
</script>

<style lang="scss" scoped>
.newsletter {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  margin-block: 40px;
  &__title {
    color: black;
    font-weight: 600;
    font-size: 24px;
    text-align: center;
    span {
      color: #8720ac;
      font-weight: 700;
      font-size: 24px;
      margin-right: 5px;
    }
  }
  &__subtitle {
    font-weight: 400;
    font-size: 1rem;
    color: #737373;
  }
  form {
    padding-block: 15px;
    max-width: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    max-width: 440px;
    @media screen and (max-width: 375px) {
        max-width: unset;
        flex-direction: column;
    }
    .input-text {
      width: 60%;
      border: 1px solid #222;
      background: white;
      padding: 5px 0 5px 10px;
      height: 36px;
      outline: none;
      @media screen and (max-width: 425px) {
        max-width: 180px;
      }
      @media screen and (max-width: 375px) {
        max-width: unset;
        width: 100% !important;
      }
    }
    .input-submit {
      width: 40%;
      height: 36px;
      border: none;
      background: #222;
      color: white;
      font-weight: 600;
      line-height: 36px;
      cursor: pointer;
      @media screen and (max-width: 425px) {
        width: unset !important;
        padding-inline: 15px;
      }
      @media screen and (max-width: 375px) {
        max-width: unset;
        width: 100% !important;
        text-align: center;
      }
    }
  }
  &__description {
    color: #b8c6d9;
    font-weight: 400;
    font-size: 1rem;
    text-align: center;
  }
  .newsletter__success--backdrop {
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0);
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
    display: flex;
    transition: all 0.3s linear;
    opacity: 0;
    visibility: hidden;
    &.active {
      background: rgba(0, 0, 0, 0.4);
      z-index: 99998;
      opacity: 1;
      visibility: visible;
    }
  }
  .newsletter__success {
    position: fixed;
    top: 50%;
    left: 50%;
    background: white;
    z-index: 301;
    transform: translate(-50%, -50%);
    width: 100%;
    max-width:500px;
    height: 300px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    z-index: -1;
    visibility: hidden;
    opacity: 0;
    border-radius: 5px;
    &.active {
      z-index: 99999;
      visibility: visible;
      opacity: 1;
    }
    .close-icon {
      background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTgiIGhlaWdodD0iMTgiIHZpZXdCb3g9IjAgMCAxOCAxOCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik0yLjQ2OTY3IDIuNDY5NjdDMi43NjI1NiAyLjE3Njc4IDMuMjM3NDQgMi4xNzY3OCAzLjUzMDMzIDIuNDY5NjdMOSA3LjkzOTM0TDE0LjQ2OTcgMi40Njk2N0MxNC43NjI2IDIuMTc2NzggMTUuMjM3NCAyLjE3Njc4IDE1LjUzMDMgMi40Njk2N0MxNS44MjMyIDIuNzYyNTYgMTUuODIzMiAzLjIzNzQ0IDE1LjUzMDMgMy41MzAzM0wxMC4wNjA3IDlMMTUuNTMwMyAxNC40Njk3QzE1LjgyMzIgMTQuNzYyNiAxNS44MjMyIDE1LjIzNzQgMTUuNTMwMyAxNS41MzAzQzE1LjIzNzQgMTUuODIzMiAxNC43NjI2IDE1LjgyMzIgMTQuNDY5NyAxNS41MzAzTDkgMTAuMDYwN0wzLjUzMDMzIDE1LjUzMDNDMy4yMzc0NCAxNS44MjMyIDIuNzYyNTYgMTUuODIzMiAyLjQ2OTY3IDE1LjUzMDNDMi4xNzY3OCAxNS4yMzc0IDIuMTc2NzggMTQuNzYyNiAyLjQ2OTY3IDE0LjQ2OTdMNy45MzkzNCA5TDIuNDY5NjcgMy41MzAzM0MyLjE3Njc4IDMuMjM3NDQgMi4xNzY3OCAyLjc2MjU2IDIuNDY5NjcgMi40Njk2N1oiIGZpbGw9ImJsYWNrIi8+Cjwvc3ZnPgo=)
        no-repeat center;
      width: 20px;
      height: 20px;
      display: inline-block;
      cursor: pointer;
      background-size: 100%;
      position: absolute;
      top: 20px;
      right: 20px;
    }
    h3 {
      font-size: 32px;
      text-transform: uppercase;
    }
    span {
      margin-bottom: 20px;
      color: #737373;
      text-transform: uppercase;
    }
    #coupon {
      width: fit-content;
      padding: 10px 20px;
      border: 1px solid black;
      margin-bottom: 10px;
      text-align: center;
      outline: none;
    }
    button {
      width: fit-content;
      padding: 10px 30px;
      border: none;
      background: #222;
      color: white;
      text-transform: uppercase;
      cursor: pointer;
    }
  }
}
</style>