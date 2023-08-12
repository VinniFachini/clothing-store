<template>
  <footer class="footer">
    <section class="footer-info container">
      <article class="footer-article">
        <h3 class="footer-article__title">Institutional</h3>
        <ul class="footer-article__list">
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">The Brand</a></h4>
          </li>
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">About Us</a></h4>
          </li>
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">Our Team</a></h4>
          </li>
        </ul>
      </article>
      <article class="footer-article">
        <h3 class="footer-article__title">Your Account</h3>
        <ul class="footer-article__list">
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">Pannel</a></h4>
          </li>
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">My Orders</a></h4>
          </li>
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">My Data</a></h4>
          </li>
        </ul>
      </article>
      <article class="footer-article">
        <h3 class="footer-article__title">Customer Service</h3>
        <ul class="footer-article__list">
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">Talk to Us</a></h4>
          </li>
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">FAQ</a></h4>
          </li>
          <li class="footer-article__list__item">
            <h4>
              <a target="_blank" href="https://google.com"
                >Exchanges and Returns</a
              >
            </h4>
          </li>
          <li class="footer-article__list__item">
            <h4><a target="_blank" href="https://google.com">Warranty</a></h4>
          </li>
          <li class="footer-article__list__item">
            <h4>
              <a target="_blank" href="https://google.com">Privacy Policy</a>
            </h4>
          </li>
          <li class="footer-article__list__item">
            <h4>
              <a target="_blank" href="https://google.com">Refund Policy</a>
            </h4>
          </li>
          <li class="footer-article__list__item">
            <h4>
              <a target="_blank" href="https://google.com">Shipping Policy</a>
            </h4>
          </li>
        </ul>
      </article>
      <article class="footer-article">
        <h3 class="footer-article__title">Contact</h3>
        <div class="footer-article__contact">
          <div class="footer-article__contact__email">email@company.com</div>
          <div class="footer-article__contact__telephone-number">
            +1 (907) 283-0548
          </div>
          <div class="footer-article__contact__social-media">
            <div class="instagram"></div>
            <div class="facebook"></div>
          </div>
        </div>
      </article>
      <article class="footer-article">
        <h3 class="footer-article__title">Address</h3>
        <div class="footer-article__address">
          <span class="address"
            >161 Trumpeter Ave, Soldotna, Alaska 99669, USA</span
          >
        </div>
      </article>
    </section>
    <section class="footer-rights">
      Made with love by
      <strong
        ><a target="_blank" href="https://github.com/VinniFachini"
          >VinniFachini</a
        ></strong
      >
    </section>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  padding-top: 40px;
  margin-top: 80px;
  background-color: #222;
  color: white;
  &-info {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    padding-bottom: 40px;
    .footer-article {
      .footer-article__title {
        font-size: 1.4rem;
      }
      .footer-article__list {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: flex-start;
        row-gap: 5px;
        .footer-article__list__item {
          width: 100%;
          h4 {
            transition: all 0.1s linear;
            font-size: 1rem;
            font-weight: 500;
            width: fit-content;
            &:hover {
              transform: translateX(10px);
              a {
                color: #ddd;
              }
            }
          }
        }
      }
    }
  }
  &-rights {
    padding-block: 20px;
    text-align: center;
    position: relative;
    border-top: 1px solid #cccccc;
  }
}
</style>