<template>
  <section class="newsletter container">
    <h3 class="newsletter__title"><span>Get $20 OFF</span>in your first purchase!</h3>
    <span class="newsletter__subtitle">Valid for purchases above $100</span>
    <form method="POST">
        <input class="input-text" type="text" name="email" id="email" placeholder="Type your e-mail">
        <input class="input-submit" type="submit" name="email" value="I WANT MY COUPON" id="email">
    </form>
    <span class="newsletter__description">We respect your privacy, we only send e-mails about our products</span>
  </section>
</template>

<script>
export default {

}
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
        .input-text {
            width: 60%;
            border: 1px solid #222;
            border-right: none;
            background: white;
            padding: 5px 0 5px 10px;
            height: 36px;
            outline: none;
        }
        .input-submit {
            width: 40%;
            height: 36px;
            border: none;
            background: #222;
            color: white;
            font-weight: 600;
            line-height: 36px;
        }
    }
    &__description {
        color: #b8c6d9;
        font-weight: 400;
        font-size: 1rem;
    }
}

</style>