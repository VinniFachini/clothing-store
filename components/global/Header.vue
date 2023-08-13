<template>
  <header class="header">
    <div class="first-bar">
      <span class="first-bar__announcment container"
        >10% OFF NO PIX | FRETE GRÁTIS EM COMPRAS ACIMA DE R$ 347</span
      >
    </div>
    <div class="second-bar container">
      <div class="mobile-nav">
        <span class="mobile-nav__icon" @click="toggleMobileMenu"></span>
        <div class="mobile-nav__container" :class="{ active: menuMobile }">
          <div class="mobile-nav__header">
            <span
              class="mobile-nav__icon active"
              @click="toggleMobileMenu"
            ></span>
            <div class="mobile-nav__logo">
              <NuxtLink to="/">
                <h1>Clothing Store</h1>
              </NuxtLink>
            </div>
          </div>
          <form class="search-mobile" action="search" method="get">
            <input
              placeholder="Search on Clothing Store"
              type="text"
              name="query"
              id="query"
            />
            <button type="submit">
              <span class="search-icon"></span>
            </button>
          </form>
          <nav class="menu-mobile">
            <ul class="menu-mobile__container">
              <li class="menu-mobile__item"  @click="toggleMenuMobileExtendedBestSellers" :class="{ active: menuMobileExtendedBestSellers }">
                <NuxtLink to="/">Best Sellers</NuxtLink>
                <ul class="menu-mobile__item__subitem-wrapper">
                  <h3>Best Sellers</h3>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Best Sellers</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Best Sellers</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Best Sellers</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Best Sellers</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Best Sellers</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Best Sellers</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Best Sellers</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Best Sellers</NuxtLink>
                  </li>
                </ul>
              </li>
              <li class="menu-mobile__item">
                <NuxtLink to="/">Tênis</NuxtLink>
              </li>
              <li class="menu-mobile__item">
                <NuxtLink to="/">Acessórios</NuxtLink>
              </li>
              <li class="menu-mobile__item" @click="toggleMenuMobileExtendedOutlet" :class="{ active: menuMobileExtendedOutlet }">
                <NuxtLink to="/">Outlet</NuxtLink>
                <ul class="menu-mobile__item__subitem-wrapper">
                  <h3>Outlet</h3>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Outlet</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Outlet</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Outlet</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Outlet</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Outlet</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Outlet</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Outlet</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Outlet</NuxtLink>
                  </li>
                </ul>
              </li>
              <li class="menu-mobile__item" @click="toggleMenuMobileExtendedCamisetas" :class="{ active: menuMobileExtendedCamisetas }">
                <NuxtLink to="/">Camisetas</NuxtLink>
                <ul class="menu-mobile__item__subitem-wrapper">
                  <h3>Camisetas</h3>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Camisetas</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Camisetas</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Camisetas</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Camisetas</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Camisetas</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Camisetas</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Camisetas</NuxtLink>
                  </li>
                  <li class="menu-mobile__item__subitem-wrapper__subitem">
                    <NuxtLink to="/">Camisetas</NuxtLink>
                  </li>
                </ul>
              </li>
            </ul>
          </nav>
        </div>
      </div>
      <div class="second-bar__logo">
        <NuxtLink to="/">
          <h1>Clothing Store</h1>
        </NuxtLink>
      </div>
      <nav class="second-bar__nav-menu">
        <ul class="menu-desktop">
          <li class="menu-desktop__item">
            <NuxtLink to="/">Best Sellers</NuxtLink>
            <ul class="menu-desktop__item__subitem-wrapper">
              <h3>Best Sellers</h3>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Best Sellers</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Best Sellers</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Best Sellers</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Best Sellers</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Best Sellers</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Best Sellers</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Best Sellers</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Best Sellers</NuxtLink>
              </li>
            </ul>
          </li>
          <li class="menu-desktop__item">
            <NuxtLink to="/">Tênis</NuxtLink>
          </li>
          <li class="menu-desktop__item">
            <NuxtLink to="/">Acessórios</NuxtLink>
          </li>
          <li class="menu-desktop__item">
            <NuxtLink to="/">Outlet</NuxtLink>
            <ul class="menu-desktop__item__subitem-wrapper">
              <h3>Outlet</h3>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Outlet</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Outlet</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Outlet</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Outlet</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Outlet</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Outlet</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Outlet</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Outlet</NuxtLink>
              </li>
            </ul>
          </li>
          <li class="menu-desktop__item">
            <NuxtLink to="/">Camisetas</NuxtLink>
            <ul class="menu-desktop__item__subitem-wrapper">
              <h3>Camisetas</h3>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Camisetas</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Camisetas</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Camisetas</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Camisetas</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Camisetas</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Camisetas</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Camisetas</NuxtLink>
              </li>
              <li class="menu-desktop__item__subitem-wrapper__subitem">
                <NuxtLink to="/">Camisetas</NuxtLink>
              </li>
            </ul>
          </li>
        </ul>
      </nav>
      <div class="second-bar__function-buttons">
        <form action="search" method="get">
          <input
            placeholder="Search on Clothing Store"
            type="text"
            name="query"
            id="query"
          />
          <button type="submit">
            <span class="search-icon"></span>
          </button>
        </form>
        <div class="my-account">
          <span class="my-account__icon">
            <ul class="actions-wrapper">
              <li class="actions-wrapper__item">
                <NuxtLink to="/">Login</NuxtLink>
              </li>
              <li class="actions-wrapper__item">
                <NuxtLink to="/">Register</NuxtLink>
              </li>
            </ul>
          </span>
        </div>
        <div class="cart">
          <span class="cart__icon" @click="toggleCart"></span>
          <div
            class="cart-backdrop"
            @click="toggleCart"
            :class="{ active: isActive }"
          ></div>
          <div class="cart-content" :class="{ active: isActive }">
            <div class="cart-content__header">
              <h3 class="cart-content__title">Cart</h3>
              <span class="close-cart-icon" @click="toggleCart"></span>
            </div>
            <div class="cart-content__items"></div>
            <div class="cart-content__footer">
              <span class="total">
                <div class="total__label">Subtotal:</div>
                <b class="total__price">R$ 0</b>
              </span>
              <NuxtLink to="/">Close Order</NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>
 
<style lang="scss" scoped>
.header {
  width: 100%;
  box-shadow: 0px 0px 5px -3px;
  .first-bar {
    width: 100%;
    background-color: black;
    &__announcment {
      color: white;
      text-align: center;
      display: block;
      padding-block: 5px;
      font-size: 12px;
      font-weight: 500;
    }
  }
  .second-bar {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    place-items: center;
    .mobile-nav {
      display: none;
    }
    &__logo,
    .mobile-nav__logo {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: flex-start;
      h1 {
        text-indent: -999999px;
        background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjA4IiBoZWlnaHQ9IjUzIiB2aWV3Qm94PSIwIDAgMjA4IDUzIiBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgo8cGF0aCBkPSJNNTguMTIgMjUuNkM1OC4xMiAyNi44OTYgNTguNDA4IDI4LjA0IDU4Ljk4NCAyOS4wMzJDNTkuNTc2IDMwLjAyNCA2MC4zNDQgMzAuOCA2MS4yODggMzEuMzZDNjIuMjMyIDMxLjkyIDYzLjI1NiAzMi4yIDY0LjM2IDMyLjJDNjUuMTYgMzIuMiA2NS44ODggMzIuMDk2IDY2LjU0NCAzMS44ODhDNjcuMjE2IDMxLjY4IDY3LjgyNCAzMS4zOTIgNjguMzY4IDMxLjAyNEM2OC45MTIgMzAuNjQgNjkuMzc2IDMwLjIgNjkuNzYgMjkuNzA0VjMyLjM5MkM2OS4wNTYgMzMuMDE2IDY4LjI4OCAzMy40OCA2Ny40NTYgMzMuNzg0QzY2LjYyNCAzNC4wODggNjUuNTkyIDM0LjI0IDY0LjM2IDM0LjI0QzYzLjE5MiAzNC4yNCA2Mi4wOTYgMzQuMDMyIDYxLjA3MiAzMy42MTZDNjAuMDY0IDMzLjE4NCA1OS4xNzYgMzIuNTg0IDU4LjQwOCAzMS44MTZDNTcuNjQgMzEuMDMyIDU3LjA0IDMwLjExMiA1Ni42MDggMjkuMDU2QzU2LjE3NiAyOCA1NS45NiAyNi44NDggNTUuOTYgMjUuNkM1NS45NiAyNC4zNTIgNTYuMTc2IDIzLjIgNTYuNjA4IDIyLjE0NEM1Ny4wNCAyMS4wODggNTcuNjQgMjAuMTc2IDU4LjQwOCAxOS40MDhDNTkuMTc2IDE4LjYyNCA2MC4wNjQgMTguMDI0IDYxLjA3MiAxNy42MDhDNjIuMDk2IDE3LjE3NiA2My4xOTIgMTYuOTYgNjQuMzYgMTYuOTZDNjUuNTkyIDE2Ljk2IDY2LjYyNCAxNy4xMTIgNjcuNDU2IDE3LjQxNkM2OC4yODggMTcuNzIgNjkuMDU2IDE4LjE4NCA2OS43NiAxOC44MDhWMjEuNDk2QzY5LjM3NiAyMSA2OC45MTIgMjAuNTY4IDY4LjM2OCAyMC4yQzY3LjgyNCAxOS44MTYgNjcuMjE2IDE5LjUyIDY2LjU0NCAxOS4zMTJDNjUuODg4IDE5LjEwNCA2NS4xNiAxOSA2NC4zNiAxOUM2My4yNTYgMTkgNjIuMjMyIDE5LjI4IDYxLjI4OCAxOS44NEM2MC4zNDQgMjAuNCA1OS41NzYgMjEuMTc2IDU4Ljk4NCAyMi4xNjhDNTguNDA4IDIzLjE0NCA1OC4xMiAyNC4yODggNTguMTIgMjUuNlpNNzMuMjI5NyAxNS4yOEg3NS4xNDk3VjM0SDczLjIyOTdWMTUuMjhaTTc3LjgwMDkgMjguNDhDNzcuODAwOSAyNy4zNiA3OC4wNDg5IDI2LjM2OCA3OC41NDQ5IDI1LjUwNEM3OS4wNTY5IDI0LjY0IDc5Ljc0NDkgMjMuOTYgODAuNjA4OSAyMy40NjRDODEuNDcyOSAyMi45NjggODIuNDQwOSAyMi43MiA4My41MTI5IDIyLjcyQzg0LjYwMDkgMjIuNzIgODUuNTY4OSAyMi45NjggODYuNDE2OSAyMy40NjRDODcuMjgwOSAyMy45NiA4Ny45NjA5IDI0LjY0IDg4LjQ1NjkgMjUuNTA0Qzg4Ljk2ODkgMjYuMzY4IDg5LjIyNDkgMjcuMzYgODkuMjI0OSAyOC40OEM4OS4yMjQ5IDI5LjU4NCA4OC45Njg5IDMwLjU3NiA4OC40NTY5IDMxLjQ1NkM4Ny45NjA5IDMyLjMyIDg3LjI4MDkgMzMgODYuNDE2OSAzMy40OTZDODUuNTY4OSAzMy45OTIgODQuNjAwOSAzNC4yNCA4My41MTI5IDM0LjI0QzgyLjQ0MDkgMzQuMjQgODEuNDcyOSAzMy45OTIgODAuNjA4OSAzMy40OTZDNzkuNzQ0OSAzMyA3OS4wNTY5IDMyLjMyIDc4LjU0NDkgMzEuNDU2Qzc4LjA0ODkgMzAuNTc2IDc3LjgwMDkgMjkuNTg0IDc3LjgwMDkgMjguNDhaTTc5Ljc0NDkgMjguNDhDNzkuNzQ0OSAyOS4yNDggNzkuOTA0OSAyOS45MjggODAuMjI0OSAzMC41MkM4MC41NjA5IDMxLjExMiA4MS4wMDg5IDMxLjU4NCA4MS41Njg5IDMxLjkzNkM4Mi4xNDQ5IDMyLjI3MiA4Mi43OTI5IDMyLjQ0IDgzLjUxMjkgMzIuNDRDODQuMjMyOSAzMi40NCA4NC44NzI5IDMyLjI3MiA4NS40MzI5IDMxLjkzNkM4Ni4wMDg5IDMxLjU4NCA4Ni40NTY5IDMxLjExMiA4Ni43NzY5IDMwLjUyQzg3LjExMjkgMjkuOTI4IDg3LjI4MDkgMjkuMjQ4IDg3LjI4MDkgMjguNDhDODcuMjgwOSAyNy43MTIgODcuMTEyOSAyNy4wMzIgODYuNzc2OSAyNi40NEM4Ni40NTY5IDI1LjgzMiA4Ni4wMDg5IDI1LjM2IDg1LjQzMjkgMjUuMDI0Qzg0Ljg3MjkgMjQuNjg4IDg0LjIzMjkgMjQuNTIgODMuNTEyOSAyNC41MkM4Mi43OTI5IDI0LjUyIDgyLjE0NDkgMjQuNjg4IDgxLjU2ODkgMjUuMDI0QzgxLjAwODkgMjUuMzYgODAuNTYwOSAyNS44MzIgODAuMjI0OSAyNi40NEM3OS45MDQ5IDI3LjAzMiA3OS43NDQ5IDI3LjcxMiA3OS43NDQ5IDI4LjQ4Wk05MC4xODI1IDIyLjk2SDk1LjcwMjVWMjQuNzZIOTAuMTgyNVYyMi45NlpNOTEuOTgyNSAxOS4xMkg5My45MDI1VjM0SDkxLjk4MjVWMTkuMTJaTTk5LjU0ODEgMTUuMjhWMzRIOTcuNjI4MVYxNS4yOEg5OS41NDgxWk0xMDQuNzA4IDI3LjI4QzEwNC43MDggMjYuMzY4IDEwNC41MDggMjUuNjggMTA0LjEwOCAyNS4yMTZDMTAzLjcyNCAyNC43NTIgMTAzLjE0IDI0LjUyIDEwMi4zNTYgMjQuNTJDMTAxLjc5NiAyNC41MiAxMDEuMyAyNC42NCAxMDAuODY4IDI0Ljg4QzEwMC40NTIgMjUuMTIgMTAwLjEyNCAyNS40NDggOTkuODg0MSAyNS44NjRDOTkuNjYwMSAyNi4yOCA5OS41NDgxIDI2Ljc1MiA5OS41NDgxIDI3LjI4SDk4LjkyNDFDOTguOTI0MSAyNi40IDk5LjA5MjEgMjUuNjI0IDk5LjQyODEgMjQuOTUyQzk5Ljc2NDEgMjQuMjY0IDEwMC4yMiAyMy43MiAxMDAuNzk2IDIzLjMyQzEwMS4zODggMjIuOTIgMTAyLjA2OCAyMi43MiAxMDIuODM2IDIyLjcyQzEwMy42MDQgMjIuNzIgMTA0LjI2OCAyMi44OCAxMDQuODI4IDIzLjJDMTA1LjQwNCAyMy41MiAxMDUuODQ0IDI0IDEwNi4xNDggMjQuNjRDMTA2LjQ2OCAyNS4yOCAxMDYuNjI4IDI2LjA4IDEwNi42MjggMjcuMDRWMzRIMTA0LjcwOFYyNy4yOFpNMTEwLjIzOCAxOC40QzExMC4yMzggMTguMDMyIDExMC4zNjYgMTcuNzIgMTEwLjYyMiAxNy40NjRDMTEwLjg5NCAxNy4yMDggMTExLjIwNiAxNy4wOCAxMTEuNTU4IDE3LjA4QzExMS45MjYgMTcuMDggMTEyLjIzOCAxNy4yMDggMTEyLjQ5NCAxNy40NjRDMTEyLjc1IDE3LjcyIDExMi44NzggMTguMDMyIDExMi44NzggMTguNEMxMTIuODc4IDE4Ljc1MiAxMTIuNzUgMTkuMDY0IDExMi40OTQgMTkuMzM2QzExMi4yMzggMTkuNTkyIDExMS45MjYgMTkuNzIgMTExLjU1OCAxOS43MkMxMTEuMjA2IDE5LjcyIDExMC44OTQgMTkuNTkyIDExMC42MjIgMTkuMzM2QzExMC4zNjYgMTkuMDY0IDExMC4yMzggMTguNzUyIDExMC4yMzggMTguNFpNMTEwLjU5OCAyMi45NkgxMTIuNTE4VjM0SDExMC41OThWMjIuOTZaTTEyMy41NTIgMjcuMjhDMTIzLjU1MiAyNi4zNjggMTIzLjM1MiAyNS42OCAxMjIuOTUyIDI1LjIxNkMxMjIuNTUyIDI0Ljc1MiAxMjEuOTY4IDI0LjUyIDEyMS4yIDI0LjUyQzEyMC42NCAyNC41MiAxMjAuMTQ0IDI0LjY0IDExOS43MTIgMjQuODhDMTE5LjI5NiAyNS4xMDQgMTE4Ljk2OCAyNS40MjQgMTE4LjcyOCAyNS44NEMxMTguNTA0IDI2LjI1NiAxMTguMzkyIDI2LjczNiAxMTguMzkyIDI3LjI4VjM0SDExNi40NzJWMjIuOTZIMTE4LjM5MlYyNC42ODhDMTE4Ljc2IDI0LjAxNiAxMTkuMjE2IDIzLjUyIDExOS43NiAyMy4yQzEyMC4zMiAyMi44OCAxMjAuOTYgMjIuNzIgMTIxLjY4IDIyLjcyQzEyMi44NDggMjIuNzIgMTIzLjc2OCAyMy4xMTIgMTI0LjQ0IDIzLjg5NkMxMjUuMTI4IDI0LjY2NCAxMjUuNDcyIDI1LjcxMiAxMjUuNDcyIDI3LjA0VjM0SDEyMy41NTJWMjcuMjhaTTEyOC4zMzcgMzQuNzJIMTMwLjI4MUMxMzAuMjgxIDM1LjI0OCAxMzAuNDI1IDM1LjczNiAxMzAuNzEzIDM2LjE4NEMxMzEuMDAxIDM2LjY0OCAxMzEuNDA5IDM3LjAxNiAxMzEuOTM3IDM3LjI4OEMxMzIuNDY1IDM3LjU3NiAxMzMuMDg5IDM3LjcyIDEzMy44MDkgMzcuNzJDMTM0LjM2OSAzNy43MiAxMzQuOTIxIDM3LjU4NCAxMzUuNDY1IDM3LjMxMkMxMzYuMDA5IDM3LjA0IDEzNi40NTcgMzYuNjA4IDEzNi44MDkgMzYuMDE2QzEzNy4xNzcgMzUuNDQgMTM3LjM2MSAzNC42ODggMTM3LjM2MSAzMy43NlYyMi45NkgxMzkuMjgxVjMzLjc2QzEzOS4yODEgMzUuMDI0IDEzOS4wMTcgMzYuMDggMTM4LjQ4OSAzNi45MjhDMTM3Ljk2MSAzNy43OTIgMTM3LjI4MSAzOC40NCAxMzYuNDQ5IDM4Ljg3MkMxMzUuNjE3IDM5LjMwNCAxMzQuNzM3IDM5LjUyIDEzMy44MDkgMzkuNTJDMTMyLjczNyAzOS41MiAxMzEuNzg1IDM5LjMyIDEzMC45NTMgMzguOTJDMTMwLjEzNyAzOC41MiAxMjkuNDk3IDM3Ljk1MiAxMjkuMDMzIDM3LjIxNkMxMjguNTY5IDM2LjQ5NiAxMjguMzM3IDM1LjY2NCAxMjguMzM3IDM0LjcyWk0xMjguMTIxIDI4LjQ4QzEyOC4xMjEgMjcuMjggMTI4LjM2OSAyNi4yNTYgMTI4Ljg2NSAyNS40MDhDMTI5LjM2MSAyNC41NDQgMTMwLjAyNSAyMy44OCAxMzAuODU3IDIzLjQxNkMxMzEuNjg5IDIyLjk1MiAxMzIuNjAxIDIyLjcyIDEzMy41OTMgMjIuNzJDMTM0LjUyMSAyMi43MiAxMzUuMzI5IDIyLjk1MiAxMzYuMDE3IDIzLjQxNkMxMzYuNzA1IDIzLjg4IDEzNy4yNDEgMjQuNTQ0IDEzNy42MjUgMjUuNDA4QzEzOC4wMjUgMjYuMjU2IDEzOC4yMjUgMjcuMjggMTM4LjIyNSAyOC40OEMxMzguMjI1IDI5LjY2NCAxMzguMDI1IDMwLjY4OCAxMzcuNjI1IDMxLjU1MkMxMzcuMjQxIDMyLjQxNiAxMzYuNzA1IDMzLjA4IDEzNi4wMTcgMzMuNTQ0QzEzNS4zMjkgMzQuMDA4IDEzNC41MjEgMzQuMjQgMTMzLjU5MyAzNC4yNEMxMzIuNjAxIDM0LjI0IDEzMS42ODkgMzQuMDA4IDEzMC44NTcgMzMuNTQ0QzEzMC4wMjUgMzMuMDggMTI5LjM2MSAzMi40MTYgMTI4Ljg2NSAzMS41NTJDMTI4LjM2OSAzMC42ODggMTI4LjEyMSAyOS42NjQgMTI4LjEyMSAyOC40OFpNMTMwLjA2NSAyOC40OEMxMzAuMDY1IDI5LjMyOCAxMzAuMjMzIDMwLjA0OCAxMzAuNTY5IDMwLjY0QzEzMC45MjEgMzEuMjMyIDEzMS4zODUgMzEuNjggMTMxLjk2MSAzMS45ODRDMTMyLjUzNyAzMi4yODggMTMzLjE2MSAzMi40NCAxMzMuODMzIDMyLjQ0QzEzNC4zOTMgMzIuNDQgMTM0Ljk0NSAzMi4yODggMTM1LjQ4OSAzMS45ODRDMTM2LjAzMyAzMS42OCAxMzYuNDgxIDMxLjIzMiAxMzYuODMzIDMwLjY0QzEzNy4xODUgMzAuMDQ4IDEzNy4zNjEgMjkuMzI4IDEzNy4zNjEgMjguNDhDMTM3LjM2MSAyNy44NCAxMzcuMjU3IDI3LjI4IDEzNy4wNDkgMjYuOEMxMzYuODQxIDI2LjMwNCAxMzYuNTYxIDI1Ljg4OCAxMzYuMjA5IDI1LjU1MkMxMzUuODczIDI1LjIxNiAxMzUuNDk3IDI0Ljk2IDEzNS4wODEgMjQuNzg0QzEzNC42NjUgMjQuNjA4IDEzNC4yNDkgMjQuNTIgMTMzLjgzMyAyNC41MkMxMzMuMTYxIDI0LjUyIDEzMi41MzcgMjQuNjcyIDEzMS45NjEgMjQuOTc2QzEzMS4zODUgMjUuMjggMTMwLjkyMSAyNS43MjggMTMwLjU2OSAyNi4zMkMxMzAuMjMzIDI2LjkxMiAxMzAuMDY1IDI3LjYzMiAxMzAuMDY1IDI4LjQ4Wk0xNTAuNzA4IDI4LjkxMkMxNTEuMDkyIDI5LjU4NCAxNTEuNDkyIDMwLjE3NiAxNTEuOTA4IDMwLjY4OEMxNTIuMzQgMzEuMiAxNTIuODIgMzEuNiAxNTMuMzQ4IDMxLjg4OEMxNTMuODc2IDMyLjE3NiAxNTQuNDc2IDMyLjMyIDE1NS4xNDggMzIuMzJDMTU2LjA0NCAzMi4zMiAxNTYuNzY0IDMyLjA3MiAxNTcuMzA4IDMxLjU3NkMxNTcuODUyIDMxLjA4IDE1OC4xMjQgMzAuNDQ4IDE1OC4xMjQgMjkuNjhDMTU4LjEyNCAyOC45MjggMTU3Ljk0OCAyOC4zMjggMTU3LjU5NiAyNy44OEMxNTcuMjQ0IDI3LjQzMiAxNTYuNzggMjcuMDcyIDE1Ni4yMDQgMjYuOEMxNTUuNjQ0IDI2LjUxMiAxNTUuMDQ0IDI2LjI1NiAxNTQuNDA0IDI2LjAzMkMxNTMuOTg4IDI1Ljg4OCAxNTMuNTI0IDI1LjcwNCAxNTMuMDEyIDI1LjQ4QzE1Mi41IDI1LjI0IDE1Mi4wMTIgMjQuOTQ0IDE1MS41NDggMjQuNTkyQzE1MS4wODQgMjQuMjI0IDE1MC43IDIzLjc3NiAxNTAuMzk2IDIzLjI0OEMxNTAuMTA4IDIyLjcyIDE0OS45NjQgMjIuMDcyIDE0OS45NjQgMjEuMzA0QzE0OS45NjQgMjAuNDcyIDE1MC4xNzIgMTkuNzI4IDE1MC41ODggMTkuMDcyQzE1MS4wMDQgMTguNDE2IDE1MS41OCAxNy45MDQgMTUyLjMxNiAxNy41MzZDMTUzLjA1MiAxNy4xNTIgMTUzLjg5MiAxNi45NiAxNTQuODM2IDE2Ljk2QzE1NS43NDggMTYuOTYgMTU2LjU0IDE3LjEzNiAxNTcuMjEyIDE3LjQ4OEMxNTcuOSAxNy44MjQgMTU4LjQ4NCAxOC4yNjQgMTU4Ljk2NCAxOC44MDhDMTU5LjQ0NCAxOS4zMzYgMTU5LjgyIDE5Ljg5NiAxNjAuMDkyIDIwLjQ4OEwxNTguMzQgMjEuNDk2QzE1OC4xMzIgMjEuMDggMTU3Ljg2OCAyMC42NzIgMTU3LjU0OCAyMC4yNzJDMTU3LjIyOCAxOS44NzIgMTU2LjgzNiAxOS41NDQgMTU2LjM3MiAxOS4yODhDMTU1LjkyNCAxOS4wMzIgMTU1LjM3MiAxOC45MDQgMTU0LjcxNiAxOC45MDRDMTUzLjgwNCAxOC45MDQgMTUzLjE0IDE5LjEyOCAxNTIuNzI0IDE5LjU3NkMxNTIuMzA4IDIwLjAwOCAxNTIuMSAyMC40OTYgMTUyLjEgMjEuMDRDMTUyLjEgMjEuNTA0IDE1Mi4yMiAyMS45MzYgMTUyLjQ2IDIyLjMzNkMxNTIuNyAyMi43MiAxNTMuMSAyMy4wODggMTUzLjY2IDIzLjQ0QzE1NC4yMzYgMjMuNzc2IDE1NS4wMTIgMjQuMTEyIDE1NS45ODggMjQuNDQ4QzE1Ni40MzYgMjQuNjA4IDE1Ni45MDggMjQuODE2IDE1Ny40MDQgMjUuMDcyQzE1Ny45IDI1LjMyOCAxNTguMzU2IDI1LjY1NiAxNTguNzcyIDI2LjA1NkMxNTkuMjA0IDI2LjQ0IDE1OS41NTYgMjYuOTEyIDE1OS44MjggMjcuNDcyQzE2MC4xIDI4LjAxNiAxNjAuMjM2IDI4LjY3MiAxNjAuMjM2IDI5LjQ0QzE2MC4yMzYgMzAuMTc2IDE2MC4wOTIgMzAuODQgMTU5LjgwNCAzMS40MzJDMTU5LjUzMiAzMi4wMjQgMTU5LjE0OCAzMi41MjggMTU4LjY1MiAzMi45NDRDMTU4LjE3MiAzMy4zNiAxNTcuNjIgMzMuNjggMTU2Ljk5NiAzMy45MDRDMTU2LjM4OCAzNC4xMjggMTU1Ljc0OCAzNC4yNCAxNTUuMDc2IDM0LjI0QzE1NC4xNjQgMzQuMjQgMTUzLjMxNiAzNC4wNDggMTUyLjUzMiAzMy42NjRDMTUxLjc2NCAzMy4yNjQgMTUxLjA4NCAzMi43NDQgMTUwLjQ5MiAzMi4xMDRDMTQ5LjkxNiAzMS40NDggMTQ5LjQ0NCAzMC43NTIgMTQ5LjA3NiAzMC4wMTZMMTUwLjcwOCAyOC45MTJaTTE2MS40MzMgMjIuOTZIMTY2Ljk1M1YyNC43NkgxNjEuNDMzVjIyLjk2Wk0xNjMuMjMzIDE5LjEySDE2NS4xNTNWMzRIMTYzLjIzM1YxOS4xMlpNMTY3LjkxOCAyOC40OEMxNjcuOTE4IDI3LjM2IDE2OC4xNjYgMjYuMzY4IDE2OC42NjIgMjUuNTA0QzE2OS4xNzQgMjQuNjQgMTY5Ljg2MiAyMy45NiAxNzAuNzI2IDIzLjQ2NEMxNzEuNTkgMjIuOTY4IDE3Mi41NTggMjIuNzIgMTczLjYzIDIyLjcyQzE3NC43MTggMjIuNzIgMTc1LjY4NiAyMi45NjggMTc2LjUzNCAyMy40NjRDMTc3LjM5OCAyMy45NiAxNzguMDc4IDI0LjY0IDE3OC41NzQgMjUuNTA0QzE3OS4wODYgMjYuMzY4IDE3OS4zNDIgMjcuMzYgMTc5LjM0MiAyOC40OEMxNzkuMzQyIDI5LjU4NCAxNzkuMDg2IDMwLjU3NiAxNzguNTc0IDMxLjQ1NkMxNzguMDc4IDMyLjMyIDE3Ny4zOTggMzMgMTc2LjUzNCAzMy40OTZDMTc1LjY4NiAzMy45OTIgMTc0LjcxOCAzNC4yNCAxNzMuNjMgMzQuMjRDMTcyLjU1OCAzNC4yNCAxNzEuNTkgMzMuOTkyIDE3MC43MjYgMzMuNDk2QzE2OS44NjIgMzMgMTY5LjE3NCAzMi4zMiAxNjguNjYyIDMxLjQ1NkMxNjguMTY2IDMwLjU3NiAxNjcuOTE4IDI5LjU4NCAxNjcuOTE4IDI4LjQ4Wk0xNjkuODYyIDI4LjQ4QzE2OS44NjIgMjkuMjQ4IDE3MC4wMjIgMjkuOTI4IDE3MC4zNDIgMzAuNTJDMTcwLjY3OCAzMS4xMTIgMTcxLjEyNiAzMS41ODQgMTcxLjY4NiAzMS45MzZDMTcyLjI2MiAzMi4yNzIgMTcyLjkxIDMyLjQ0IDE3My42MyAzMi40NEMxNzQuMzUgMzIuNDQgMTc0Ljk5IDMyLjI3MiAxNzUuNTUgMzEuOTM2QzE3Ni4xMjYgMzEuNTg0IDE3Ni41NzQgMzEuMTEyIDE3Ni44OTQgMzAuNTJDMTc3LjIzIDI5LjkyOCAxNzcuMzk4IDI5LjI0OCAxNzcuMzk4IDI4LjQ4QzE3Ny4zOTggMjcuNzEyIDE3Ny4yMyAyNy4wMzIgMTc2Ljg5NCAyNi40NEMxNzYuNTc0IDI1LjgzMiAxNzYuMTI2IDI1LjM2IDE3NS41NSAyNS4wMjRDMTc0Ljk5IDI0LjY4OCAxNzQuMzUgMjQuNTIgMTczLjYzIDI0LjUyQzE3Mi45MSAyNC41MiAxNzIuMjYyIDI0LjY4OCAxNzEuNjg2IDI1LjAyNEMxNzEuMTI2IDI1LjM2IDE3MC42NzggMjUuODMyIDE3MC4zNDIgMjYuNDRDMTcwLjAyMiAyNy4wMzIgMTY5Ljg2MiAyNy43MTIgMTY5Ljg2MiAyOC40OFpNMTgzLjkgMjIuOTZWMzRIMTgxLjk4VjIyLjk2SDE4My45Wk0xODcuMjM2IDI1LjA3MkMxODYuOTggMjQuODggMTg2Ljc0OCAyNC43NDQgMTg2LjU0IDI0LjY2NEMxODYuMzMyIDI0LjU2OCAxODYuMDY4IDI0LjUyIDE4NS43NDggMjQuNTJDMTg1LjI2OCAyNC41MiAxODQuODkyIDI0LjY0IDE4NC42MiAyNC44OEMxODQuMzQ4IDI1LjEyIDE4NC4xNTYgMjUuNDQ4IDE4NC4wNDQgMjUuODY0QzE4My45NDggMjYuMjggMTgzLjkgMjYuNzUyIDE4My45IDI3LjI4SDE4My4wMzZDMTgzLjAzNiAyNi40IDE4My4xODggMjUuNjI0IDE4My40OTIgMjQuOTUyQzE4My44MTIgMjQuMjY0IDE4NC4yMiAyMy43MiAxODQuNzE2IDIzLjMyQzE4NS4yMTIgMjIuOTIgMTg1LjcxNiAyMi43MiAxODYuMjI4IDIyLjcyQzE4Ni42MjggMjIuNzIgMTg2Ljk5NiAyMi43NzYgMTg3LjMzMiAyMi44ODhDMTg3LjY4NCAyMi45ODQgMTg4LjAwNCAyMy4xODQgMTg4LjI5MiAyMy40ODhMMTg3LjIzNiAyNS4wNzJaTTE5NC4xMjcgMzQuMjRDMTkzLjEwMyAzNC4yNCAxOTIuMTkxIDM0IDE5MS4zOTEgMzMuNTJDMTkwLjYwNyAzMy4wMjQgMTg5Ljk5MSAzMi4zNDQgMTg5LjU0MyAzMS40OEMxODkuMTExIDMwLjYxNiAxODguODk1IDI5LjYxNiAxODguODk1IDI4LjQ4QzE4OC44OTUgMjcuMzI4IDE4OS4xMTkgMjYuMzIgMTg5LjU2NyAyNS40NTZDMTkwLjAzMSAyNC41OTIgMTkwLjY3MSAyMy45MiAxOTEuNDg3IDIzLjQ0QzE5Mi4zMTkgMjIuOTYgMTkzLjI3OSAyMi43MiAxOTQuMzY3IDIyLjcyQzE5NS40NTUgMjIuNzIgMTk2LjM4MyAyMi45NTIgMTk3LjE1MSAyMy40MTZDMTk3LjkzNSAyMy44NjQgMTk4LjUzNSAyNC41MTIgMTk4Ljk1MSAyNS4zNkMxOTkuMzY3IDI2LjIwOCAxOTkuNTc1IDI3LjIxNiAxOTkuNTc1IDI4LjM4NEMxOTkuNTc1IDI4LjQ5NiAxOTkuNTY3IDI4LjYxNiAxOTkuNTUxIDI4Ljc0NEMxOTkuNTUxIDI4Ljg1NiAxOTkuNTUxIDI4LjkyOCAxOTkuNTUxIDI4Ljk2SDE5MC4xMTlWMjcuMzI4SDE5OC4wMzlMMTk3LjI3MSAyOC40MzJDMTk3LjMxOSAyOC4zNTIgMTk3LjM2NyAyOC4yMzIgMTk3LjQxNSAyOC4wNzJDMTk3LjQ2MyAyNy44OTYgMTk3LjQ4NyAyNy43NTIgMTk3LjQ4NyAyNy42NEMxOTcuNDg3IDI2Ljk4NCAxOTcuMzUxIDI2LjQxNiAxOTcuMDc5IDI1LjkzNkMxOTYuODIzIDI1LjQ1NiAxOTYuNDYzIDI1LjA4IDE5NS45OTkgMjQuODA4QzE5NS41MzUgMjQuNTM2IDE5NC45OTEgMjQuNCAxOTQuMzY3IDI0LjRDMTkzLjYzMSAyNC40IDE5Mi45OTkgMjQuNTYgMTkyLjQ3MSAyNC44OEMxOTEuOTU5IDI1LjE4NCAxOTEuNTU5IDI1LjYzMiAxOTEuMjcxIDI2LjIyNEMxOTAuOTk5IDI2LjggMTkwLjg1NSAyNy41MTIgMTkwLjgzOSAyOC4zNkMxOTAuODM5IDI5LjIyNCAxOTAuOTc1IDI5Ljk2IDE5MS4yNDcgMzAuNTY4QzE5MS41MTkgMzEuMTc2IDE5MS45MTkgMzEuNjQgMTkyLjQ0NyAzMS45NkMxOTIuOTc1IDMyLjI4IDE5My42MTUgMzIuNDQgMTk0LjM2NyAzMi40NEMxOTUuMTE5IDMyLjQ0IDE5NS43ODMgMzIuMjggMTk2LjM1OSAzMS45NkMxOTYuOTM1IDMxLjYyNCAxOTcuNDIzIDMxLjEyIDE5Ny44MjMgMzAuNDQ4TDE5OS4zODMgMzEuNDMyQzE5OC44MDcgMzIuMzYgMTk4LjA3OSAzMy4wNjQgMTk3LjE5OSAzMy41NDRDMTk2LjMzNSAzNC4wMDggMTk1LjMxMSAzNC4yNCAxOTQuMTI3IDM0LjI0WiIgZmlsbD0idXJsKCNwYWludDBfbGluZWFyXzEwXzE2KSIvPgo8ZyBjbGlwLXBhdGg9InVybCgjY2xpcDBfMTBfMTYpIj4KPHBhdGggZD0iTTM4LjYxNTYgNS40MzY5MkwzNy45NTI4IDYuMTAxMDJWNS40MzY5MkgzNC42ODc3QzMzLjIxNTYgNy43MTE3NiAzMC4xMDc3IDkuMjg0MjIgMjYuNDk5MyA5LjI4NDIyQzIyLjg5MjMgOS4yODQyMiAxOS43ODQ0IDcuNzExNzYgMTguMzEyMyA1LjQzNjkySDE1LjA0NzJWNi4xMDEwMkwxNC4zODMxIDUuNDM2OTJMMi42NDA1NiAxNy4xODYxTDkuMDYzNzMgMjMuNjE0NUwxNS4wNDcyIDE3LjYyODRWNDcuNTYxOEgzNy45NTAxVjE3LjYyOTdMNDMuOTM1IDIzLjYxNTlMNTAuMzU2OCAxNy4xODYxTDM4LjYxNTYgNS40MzY5MloiIGZpbGw9InVybCgjcGFpbnQxX2xpbmVhcl8xMF8xNikiLz4KPHBhdGggZD0iTTM3Ljk1MDEgNTAuMjAyM0gxNS4wNDcyQzEzLjU4OTcgNTAuMjAyMyAxMi40MDY3IDQ5LjAxOTQgMTIuNDA2NyA0Ny41NjE4VjI0LjAwNTNMMTAuOTMwNiAyNS40ODE0QzEwLjQzNTUgMjUuOTc3OCA5Ljc2MzQ4IDI2LjI1NTEgOS4wNjI0MSAyNi4yNTUxQzguMzYyNjYgMjYuMjU1MSA3LjY4OTMyIDI1Ljk3NjUgNy4xOTQyMSAyNS40ODE0TDAuNzcxMDUxIDE5LjA1M0MtMC4yNTg3NjcgMTguMDIxOCAtMC4yNTg3NjcgMTYuMzUxNyAwLjc3MTA1MSAxNS4zMTkyTDEyLjUxNjMgMy41NzAwNEMxMy4wODkzIDIuOTk1NzIgMTMuOTE3MSAyLjcxNzE0IDE0LjcxNDUgMi44MTc0OEMxNC44MjQxIDIuODA0MjggMTQuOTM1IDIuNzk2MzYgMTUuMDQ3MiAyLjc5NjM2SDE4LjMxMjNDMTkuMjA3NCAyLjc5NjM2IDIwLjA0MzIgMy4yNTA1MyAyMC41MjkgNC4wMDE3N0MyMS41NjgxIDUuNjA3MjMgMjMuOTExNiA2LjY0MzY1IDI2LjQ5OTMgNi42NDM2NUMyOS4wODcxIDYuNjQzNjUgMzEuNDMxOSA1LjYwNzIzIDMyLjQ3MSA0LjAwMTc3QzMyLjk1NjggMy4yNTA1MyAzMy43OTEzIDIuNzk2MzYgMzQuNjg3NyAyLjc5NjM2SDM3Ljk1MjhDMzguMDY1IDIuNzk2MzYgMzguMTc1OSAyLjgwMjk2IDM4LjI4NTUgMi44MTc0OEMzOC4zOTM3IDIuODA0MjggMzguNTAzMyAyLjc5NjM2IDM4LjYxNDIgMi43OTYzNkMzOS4zMTQgMi43OTYzNiAzOS45ODczIDMuMDc0OTQgNDAuNDgzOCAzLjU3MDA0TDUyLjIyNjMgMTUuMzE3OUM1My4yNTYxIDE2LjM0OSA1My4yNTYxIDE4LjAxOTIgNTIuMjI2MyAxOS4wNTE2TDQ1LjgwNDUgMjUuNDgxNEM0NS4zMDk0IDI1Ljk3NjUgNDQuNjM3NCAyNi4yNTUxIDQzLjkzNzYgMjYuMjU1MUM0My4yMzc5IDI2LjI1NjQgNDIuNTY0NSAyNS45Nzc4IDQyLjA2OTQgMjUuNDgyN0w0MC41OTIgMjQuMDA0VjQ3LjU2MThDNDAuNTkwNyA0OS4wMjA3IDM5LjQwOSA1MC4yMDIzIDM3Ljk1MDEgNTAuMjAyM1pNMTcuNjg3OCA0NC45MjEySDM1LjMwOTZWMTcuNjI5N0MzNS4zMDk2IDE2LjU2MTYgMzUuOTUyNiAxNS41OTkxIDM2LjkzODggMTUuMTg5OEMzNy45MjY0IDE0Ljc3OTIgMzkuMDYwNSAxNS4wMDYzIDM5LjgxNyAxNS43NjI4TDQzLjkzMzYgMTkuODc5NUw0Ni42MjQ0IDE3LjE4NjFMMzguMTc1OSA4LjczMjMzQzM3Ljc1NDcgOC43NzA2MiAzNy4zNDAyIDguNzA0NjEgMzYuOTQyOCA4LjU0MDg5QzM2LjY2NjggOC40MjczNSAzNi40MTczIDguMjY4OTIgMzYuMjAwOCA4LjA3NzQ4SDM1Ljk3MzdDMzMuNzkzOSAxMC40ODA0IDMwLjMwMDQgMTEuOTI0OCAyNi40OTkzIDExLjkyNDhDMjIuNjk4MyAxMS45MjQ4IDE5LjIwNjEgMTAuNDgwNCAxNy4wMjUgOC4wNzc0OEgxNi43OTc5QzE2LjU4MjcgOC4yNjg5MiAxNi4zMzMyIDguNDI2MDMgMTYuMDU3MyA4LjU0MDg5QzE1LjY1NzIgOC43MDU5MyAxNS4yMzIxIDguNzY0MDIgMTQuODIxNSA4LjczMjMzTDYuMzcxNjggMTcuMTg3NEw5LjA2MjQxIDE5Ljg4MDhMMTMuMTc3NyAxNS43NjI4QzEzLjkzMjkgMTUuMDA2MyAxNS4wNjg0IDE0Ljc4MDUgMTYuMDU1OSAxNS4xODk4QzE3LjA0MzUgMTUuNTk5MSAxNy42ODY1IDE2LjU2MTYgMTcuNjg2NSAxNy42Mjk3VjQ0LjkyMTJIMTcuNjg3OFoiIGZpbGw9InVybCgjcGFpbnQyX2xpbmVhcl8xMF8xNikiLz4KPC9nPgo8ZGVmcz4KPGxpbmVhckdyYWRpZW50IGlkPSJwYWludDBfbGluZWFyXzEwXzE2IiB4MT0iNTUiIHkxPSIyMy41IiB4Mj0iMjE3LjUiIHkyPSIyMyIgZ3JhZGllbnRVbml0cz0idXNlclNwYWNlT25Vc2UiPgo8c3RvcCBzdG9wLWNvbG9yPSIjMzMzMzMzIi8+CjxzdG9wIG9mZnNldD0iMSIgc3RvcC1jb2xvcj0iIzczNzM3MyIvPgo8L2xpbmVhckdyYWRpZW50Pgo8bGluZWFyR3JhZGllbnQgaWQ9InBhaW50MV9saW5lYXJfMTBfMTYiIHgxPSIzLjA5MTkxIiB5MT0iMTguMDU4MyIgeDI9IjQ5LjkwNzgiIHkyPSIxOC4wNTgyIiBncmFkaWVudFVuaXRzPSJ1c2VyU3BhY2VPblVzZSI+CjxzdG9wIHN0b3AtY29sb3I9IiMzMzMzMzMiLz4KPHN0b3Agb2Zmc2V0PSIxIiBzdG9wLWNvbG9yPSIjNzM3MzczIi8+CjwvbGluZWFyR3JhZGllbnQ+CjxsaW5lYXJHcmFkaWVudCBpZD0icGFpbnQyX2xpbmVhcl8xMF8xNiIgeDE9IjAuNTAwMDE1IiB5MT0iMTciIHgyPSI1Mi41IiB5Mj0iMTciIGdyYWRpZW50VW5pdHM9InVzZXJTcGFjZU9uVXNlIj4KPHN0b3Agc3RvcC1jb2xvcj0iIzMzMzMzMyIvPgo8c3RvcCBvZmZzZXQ9IjEiIHN0b3AtY29sb3I9IiM3MzczNzMiLz4KPC9saW5lYXJHcmFkaWVudD4KPGNsaXBQYXRoIGlkPSJjbGlwMF8xMF8xNiI+CjxyZWN0IHdpZHRoPSI1MyIgaGVpZ2h0PSI1MyIgZmlsbD0id2hpdGUiLz4KPC9jbGlwUGF0aD4KPC9kZWZzPgo8L3N2Zz4K)
          no-repeat center;
        display: inline-block;
        background-size: 100%;
        width: 220px;
        height: 90px;
      }
    }
    &__nav-menu {
      width: 100%;
      display: flex;
      align-items: center;
      .menu-desktop {
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-between;
        &__item {
          position: relative;
          a {
            cursor: pointer;
            color: black;
            font-weight: 700;
            &:hover {
              color: #8720ac;
            }
          }
          &__subitem-wrapper {
            position: absolute;
            z-index: 999;
            top: 30px;
            left: -20px;
            width: 400px;
            padding: 20px;
            visibility: hidden;
            opacity: 0;
            transition: 0.2s linear;
            transform: translateY(-53px);
            display: flex;
            background: white;
            flex-direction: column;
            row-gap: 5px;
            box-shadow: 0px 0px 5px -3px;
            max-height: 400px;
            flex-wrap: wrap;
            h3 {
              cursor: default;
              font-size: 1.2rem;
            }
          }
          &:hover {
            .menu-desktop__item__subitem-wrapper {
              transform: translateY(0px);
              visibility: visible;
              opacity: 1;
            }
          }
        }
      }
    }
    &__function-buttons {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: flex-end;
      column-gap: 15px;
      .cart {
        width: 25px;
        height: 25px;
        &__icon {
          background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjYiIGhlaWdodD0iMjYiIHZpZXdCb3g9IjAgMCAyNiAyNiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzJfMikiPgo8bWFzayBpZD0ibWFzazBfMl8yIiBzdHlsZT0ibWFzay10eXBlOmx1bWluYW5jZSIgbWFza1VuaXRzPSJ1c2VyU3BhY2VPblVzZSIgeD0iMCIgeT0iMCIgd2lkdGg9IjI2IiBoZWlnaHQ9IjI2Ij4KPHBhdGggZD0iTTI2IDBIMFYyNkgyNlYwWiIgZmlsbD0id2hpdGUiLz4KPC9tYXNrPgo8ZyBtYXNrPSJ1cmwoI21hc2swXzJfMikiPgo8bWFzayBpZD0ibWFzazFfMl8yIiBzdHlsZT0ibWFzay10eXBlOmx1bWluYW5jZSIgbWFza1VuaXRzPSJ1c2VyU3BhY2VPblVzZSIgeD0iMCIgeT0iMCIgd2lkdGg9IjI2IiBoZWlnaHQ9IjI2Ij4KPHBhdGggZD0iTTI2IDBIMFYyNkgyNlYwWiIgZmlsbD0id2hpdGUiLz4KPC9tYXNrPgo8ZyBtYXNrPSJ1cmwoI21hc2sxXzJfMikiPgo8cGF0aCBkPSJNMjAuMjUgMjAuNUMxOC44NjI1IDIwLjUgMTcuNzUgMjEuNjEyNSAxNy43NSAyM0MxNy43NSAyMy42NjMgMTguMDEzNCAyNC4yOTg5IDE4LjQ4MjIgMjQuNzY3OEMxOC45NTExIDI1LjIzNjYgMTkuNTg3IDI1LjUgMjAuMjUgMjUuNUMyMC45MTMgMjUuNSAyMS41NDg5IDI1LjIzNjYgMjIuMDE3OCAyNC43Njc4QzIyLjQ4NjYgMjQuMjk4OSAyMi43NSAyMy42NjMgMjIuNzUgMjNDMjIuNzUgMjIuMzM3IDIyLjQ4NjYgMjEuNzAxMSAyMi4wMTc4IDIxLjIzMjJDMjEuNTQ4OSAyMC43NjM0IDIwLjkxMyAyMC41IDIwLjI1IDIwLjVaTTAuMjUgMC41VjNIMi43NUw3LjI1IDEyLjQ4NzVMNS41NSAxNS41NUM1LjM2MjUgMTUuOSA1LjI1IDE2LjMxMjUgNS4yNSAxNi43NUM1LjI1IDE3LjQxMyA1LjUxMzM5IDE4LjA0ODkgNS45ODIyMyAxOC41MTc4QzYuNDUxMDcgMTguOTg2NiA3LjA4Njk2IDE5LjI1IDcuNzUgMTkuMjVIMjIuNzVWMTYuNzVIOC4yNzVDOC4xOTIxMiAxNi43NSA4LjExMjYzIDE2LjcxNzEgOC4wNTQwMyAxNi42NTg1QzcuOTk1NDIgMTYuNTk5OSA3Ljk2MjUgMTYuNTIwNCA3Ljk2MjUgMTYuNDM3NUM3Ljk2MjUgMTYuMzc1IDcuOTc1IDE2LjMyNSA4IDE2LjI4NzVMOS4xMjUgMTQuMjVIMTguNDM3NUMxOS4zNzUgMTQuMjUgMjAuMiAxMy43MjUgMjAuNjI1IDEyLjk2MjVMMjUuMSA0Ljg3NUMyNS4xODc1IDQuNjc1IDI1LjI1IDQuNDYyNSAyNS4yNSA0LjI1QzI1LjI1IDMuOTE4NDggMjUuMTE4MyAzLjYwMDU0IDI0Ljg4MzkgMy4zNjYxMkMyNC42NDk1IDMuMTMxNyAyNC4zMzE1IDMgMjQgM0g1LjUxMjVMNC4zMzc1IDAuNU03Ljc1IDIwLjVDNi4zNjI1IDIwLjUgNS4yNSAyMS42MTI1IDUuMjUgMjNDNS4yNSAyMy42NjMgNS41MTMzOSAyNC4yOTg5IDUuOTgyMjMgMjQuNzY3OEM2LjQ1MTA3IDI1LjIzNjYgNy4wODY5NiAyNS41IDcuNzUgMjUuNUM4LjQxMzA0IDI1LjUgOS4wNDg5MyAyNS4yMzY2IDkuNTE3NzcgMjQuNzY3OEM5Ljk4NjYxIDI0LjI5ODkgMTAuMjUgMjMuNjYzIDEwLjI1IDIzQzEwLjI1IDIyLjMzNyA5Ljk4NjYxIDIxLjcwMTEgOS41MTc3NyAyMS4yMzIyQzkuMDQ4OTMgMjAuNzYzNCA4LjQxMzA0IDIwLjUgNy43NSAyMC41WiIgZmlsbD0iIzIyMjIyMiIvPgo8L2c+CjwvZz4KPC9nPgo8ZGVmcz4KPGNsaXBQYXRoIGlkPSJjbGlwMF8yXzIiPgo8cmVjdCB3aWR0aD0iMjYiIGhlaWdodD0iMjYiIGZpbGw9IndoaXRlIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==)
            no-repeat center;
          width: 25px;
          height: 25px;
          display: inline-block;
          background-size: 100%;
          cursor: pointer;
        }
        .cart-backdrop {
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
        .cart-content {
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          position: fixed;
          right: 0;
          bottom: 0;
          max-width: 500px;
          width: 100%;
          z-index: -1;
          height: 100vh;
          background: white;
          box-shadow: 0px 0px 5px -3px;
          transition: 0.3s linear;
          transform: translateX(500px);
          &.active {
            transform: translateX(0px);
            z-index: 99999;
          }
          &__header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 25px;
            border-bottom: 1px solid #ccc;
            .close-cart-icon {
              background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTgiIGhlaWdodD0iMTgiIHZpZXdCb3g9IjAgMCAxOCAxOCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik0yLjQ2OTY3IDIuNDY5NjdDMi43NjI1NiAyLjE3Njc4IDMuMjM3NDQgMi4xNzY3OCAzLjUzMDMzIDIuNDY5NjdMOSA3LjkzOTM0TDE0LjQ2OTcgMi40Njk2N0MxNC43NjI2IDIuMTc2NzggMTUuMjM3NCAyLjE3Njc4IDE1LjUzMDMgMi40Njk2N0MxNS44MjMyIDIuNzYyNTYgMTUuODIzMiAzLjIzNzQ0IDE1LjUzMDMgMy41MzAzM0wxMC4wNjA3IDlMMTUuNTMwMyAxNC40Njk3QzE1LjgyMzIgMTQuNzYyNiAxNS44MjMyIDE1LjIzNzQgMTUuNTMwMyAxNS41MzAzQzE1LjIzNzQgMTUuODIzMiAxNC43NjI2IDE1LjgyMzIgMTQuNDY5NyAxNS41MzAzTDkgMTAuMDYwN0wzLjUzMDMzIDE1LjUzMDNDMy4yMzc0NCAxNS44MjMyIDIuNzYyNTYgMTUuODIzMiAyLjQ2OTY3IDE1LjUzMDNDMi4xNzY3OCAxNS4yMzc0IDIuMTc2NzggMTQuNzYyNiAyLjQ2OTY3IDE0LjQ2OTdMNy45MzkzNCA5TDIuNDY5NjcgMy41MzAzM0MyLjE3Njc4IDMuMjM3NDQgMi4xNzY3OCAyLjc2MjU2IDIuNDY5NjcgMi40Njk2N1oiIGZpbGw9ImJsYWNrIi8+Cjwvc3ZnPgo=)
                no-repeat center;
              width: 20px;
              height: 20px;
              display: inline-block;
              cursor: pointer;
              background-size: 100%;
            }
          }
          &__footer {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            border-top: 1px solid #ccc;
            .total {
              width: 100%;
              padding: 20px 20px 10px 20px;
              display: flex;
              align-items: center;
              justify-content: space-between;
              &__label {
                font-size: 1rem;
              }
              &__price {
                font-size: 1.1rem;
              }
            }
            > a {
              width: 95%;
              margin: 0px 10px 10px 10px;
              background: #111;
              padding: 10px;
              color: white;
              text-align: center;
              text-transform: uppercase;
              transition: 0.2s;
              &:hover {
                background: #4f4f4f;
              }
            }
          }
        }
      }
      form {
        display: flex;
        align-content: center;
        justify-content: center;
        position: relative;
        input[type="text"] {
          border: none;
          outline: none;
          font-size: 0.875rem;
          padding-right: 5px;
          border-bottom: 1px solid transparent;
        }
        button[type="submit"] {
          width: 25px;
          height: 25px;
          border: none;
          background-color: transparent;
          cursor: pointer;
          .search-icon {
            background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTIxIDIxTDE2LjY1IDE2LjY1TTE5IDExQzE5IDE1LjQxODMgMTUuNDE4MyAxOSAxMSAxOUM2LjU4MTcyIDE5IDMgMTUuNDE4MyAzIDExQzMgNi41ODE3MiA2LjU4MTcyIDMgMTEgM0MxNS40MTgzIDMgMTkgNi41ODE3MiAxOSAxMVoiIHN0cm9rZT0iYmxhY2siIHN0cm9rZS13aWR0aD0iMS41IiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz4KPC9zdmc+Cg==)
              no-repeat;
            background-size: 100%;
            width: 25px;
            height: 25px;
            display: inline-block;
          }
        }
      }
      .my-account {
        position: relative;
        width: 16px;
        height: 25px;
        &__icon {
          background: url(data:image/svg+xml;base64,PHN2ZyBpZD0iR3JvdXBfMzkyIiBkYXRhLW5hbWU9Ikdyb3VwIDM5MiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iMTYuNjk0IiBoZWlnaHQ9IjIzLjY5NSIgdmlld0JveD0iMCAwIDE2LjY5NCAyMy42OTUiPgogIDxwYXRoIGlkPSJSZWN0YW5nbGVfNjk4IiBkYXRhLW5hbWU9IlJlY3RhbmdsZSA2OTgiIGQ9Ik03LjUyMywwSDkuMTcxYTcuNTIzLDcuNTIzLDAsMCwxLDcuNTIzLDcuNTIzVjEzLjg3YTAsMCwwLDAsMSwwLDBIMGEwLDAsMCwwLDEsMCwwVjcuNTIzQTcuNTIzLDcuNTIzLDAsMCwxLDcuNTIzLDBaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwIDkuODI1KSIgZmlsbD0iIzJjMmMyYyIvPgogIDxlbGxpcHNlIGlkPSJFbGxpcHNlXzE4IiBkYXRhLW5hbWU9IkVsbGlwc2UgMTgiIGN4PSIzLjg0NyIgY3k9IjMuODQ3IiByeD0iMy44NDciIHJ5PSIzLjg0NyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNC41IDApIiBmaWxsPSIjMmMyYzJjIi8+Cjwvc3ZnPgo=)
            no-repeat center;
          background-size: 100%;
          width: 16px;
          height: 25px;
          display: inline-block;
          cursor: default;
          &:hover {
            .actions-wrapper {
              transform: translateY(0px);
              visibility: visible;
              opacity: 1;
            }
          }
        }
        .actions-wrapper {
          position: absolute;
          top: 30px;
          left: -20px;
          background: white;
          padding: 10px 10px 10px 20px;
          visibility: hidden;
          opacity: 0;
          transition: 0.2s linear;
          transform: translateY(-53px);
          box-shadow: 0px 0px 5px -3px;
          z-index: 9;
          li {
            position: relative;
            a {
              color: black;
              transition: 0.2s;
              font-weight: 500;
              &:hover {
                color: #8720ac;
              }
            }
            &:hover {
              &:before {
                content: "";
                width: 5px;
                height: 3px;
                background: #8720ac;
                display: inline-block;
                position: absolute;
                top: 50%;
                left: -10px;
                transform: translateY(-50%);
              }
            }
          }
        }
      }
    }
    @media screen and (max-width: 1200px) {
      grid-template-columns: 220px 1fr 1fr !important;
    }
    @media screen and (max-width: 992px) {
      grid-template-columns: 20px 1fr 1fr !important;
      .second-bar__nav-menu {
        display: none;
      }
      &__logo h1 {
        width: 180px;
        margin-left: 20px;
      }
      .mobile-nav {
        display: flex;
        height: 80px;
        width: 32px;
        &__icon {
          background: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA0NDggNTEyIj48IS0tISBGb250IEF3ZXNvbWUgUHJvIDYuNC4yIGJ5IEBmb250YXdlc29tZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tIExpY2Vuc2UgLSBodHRwczovL2ZvbnRhd2Vzb21lLmNvbS9saWNlbnNlIChDb21tZXJjaWFsIExpY2Vuc2UpIENvcHlyaWdodCAyMDIzIEZvbnRpY29ucywgSW5jLiAtLT48cGF0aCBkPSJNMCA5NkMwIDc4LjMgMTQuMyA2NCAzMiA2NEg0MTZjMTcuNyAwIDMyIDE0LjMgMzIgMzJzLTE0LjMgMzItMzIgMzJIMzJDMTQuMyAxMjggMCAxMTMuNyAwIDk2ek0wIDI1NmMwLTE3LjcgMTQuMy0zMiAzMi0zMkg0MTZjMTcuNyAwIDMyIDE0LjMgMzIgMzJzLTE0LjMgMzItMzIgMzJIMzJjLTE3LjcgMC0zMi0xNC4zLTMyLTMyek00NDggNDE2YzAgMTcuNy0xNC4zIDMyLTMyIDMySDMyYy0xNy43IDAtMzItMTQuMy0zMi0zMnMxNC4zLTMyIDMyLTMySDQxNmMxNy43IDAgMzIgMTQuMyAzMiAzMnoiLz48L3N2Zz4=)
            no-repeat left center;
          background-size: 30px;
          cursor: pointer;
          width: 100%;
          height: 100%;
          &.active {
            width: 30px;
            height: 50px;
            display: block;
            position: absolute;
            top: 20px;
            right: 20px;
            background: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAzODQgNTEyIj48IS0tISBGb250IEF3ZXNvbWUgUHJvIDYuNC4yIGJ5IEBmb250YXdlc29tZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tIExpY2Vuc2UgLSBodHRwczovL2ZvbnRhd2Vzb21lLmNvbS9saWNlbnNlIChDb21tZXJjaWFsIExpY2Vuc2UpIENvcHlyaWdodCAyMDIzIEZvbnRpY29ucywgSW5jLiAtLT48cGF0aCBkPSJNMzQyLjYgMTUwLjZjMTIuNS0xMi41IDEyLjUtMzIuOCAwLTQ1LjNzLTMyLjgtMTIuNS00NS4zIDBMMTkyIDIxMC43IDg2LjYgMTA1LjRjLTEyLjUtMTIuNS0zMi44LTEyLjUtNDUuMyAwcy0xMi41IDMyLjggMCA0NS4zTDE0Ni43IDI1NiA0MS40IDM2MS40Yy0xMi41IDEyLjUtMTIuNSAzMi44IDAgNDUuM3MzMi44IDEyLjUgNDUuMyAwTDE5MiAzMDEuMyAyOTcuNCA0MDYuNmMxMi41IDEyLjUgMzIuOCAxMi41IDQ1LjMgMHMxMi41LTMyLjggMC00NS4zTDIzNy4zIDI1NiAzNDIuNiAxNTAuNnoiLz48L3N2Zz4=)
              no-repeat center center;
          }
        }
        &__container {
          width: 100vw;
          height: 100vh;
          background-color: white;
          position: fixed;
          top: 0;
          left: 0;
          z-index: 400;
          visibility: hidden;
          transition: all 0.2s linear;
          overflow-x: scroll;
          transform: translateX(-100%);
          &.active {
            visibility: visible;
            transform: translateX(0);
          }
          .mobile-nav__header {
            height: 90px;
            border-bottom: 1px solid #ccc;
            .mobile-nav__logo h1 {
              position: absolute;
              top: 0;
              left: 20px;
            }
          }
          .search-mobile {
            display: flex;
            align-content: center;
            justify-content: center;
            position: relative;
            width: 100%;
            border-bottom: 1px solid #ccc;
            input[type="text"] {
              border: none;
              outline: none;
              font-size: 1rem;
              padding-right: 5px;
              padding-left: 20px;
              width: calc(100% - 25px);
            }
            button[type="submit"] {
              width: 25px;
              height: 50px;
              border: none;
              background-color: transparent;
              margin-right: 20px;
              cursor: pointer;
              .search-icon {
                background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTIxIDIxTDE2LjY1IDE2LjY1TTE5IDExQzE5IDE1LjQxODMgMTUuNDE4MyAxOSAxMSAxOUM2LjU4MTcyIDE5IDMgMTUuNDE4MyAzIDExQzMgNi41ODE3MiA2LjU4MTcyIDMgMTEgM0MxNS40MTgzIDMgMTkgNi41ODE3MiAxOSAxMVoiIHN0cm9rZT0iYmxhY2siIHN0cm9rZS13aWR0aD0iMS41IiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz4KPC9zdmc+Cg==)
                  no-repeat;
                background-size: 100%;
                width: 100%;
                height: 100%;
                display: inline-block;
                background-position: center center;
              }
            }
          }
          .menu-mobile {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            &__container {
              width: 100%;
            }
            &__item {
              position: relative;
              a {
                cursor: pointer;
                color: black;
                font-weight: 700;
                display: block;
                width: 100%;
                padding: 10px 20px;
                background-color: #f1f1f1;
                border-bottom: 1px solid #ccc;
                &:hover {
                  color: #8720ac;
                }
              }
              &__subitem-wrapper {
                position: relative;
                z-index: 999;
                transition: 0.2s linear;
                visibility: hidden;
                height: 0;
                opacity: 0;
                padding-inline: 20px;
                h3 {
                  cursor: default;
                  font-size: 1.2rem;
                }
                a {
                  padding: 0 !important;
                  padding-inline: 20px !important;
                  background: none;
                  border: none;
                  padding-block: 5px !important;
                }
              }
              &.active {
                .menu-mobile__item__subitem-wrapper {
                  visibility: visible;
                  opacity: 1;
                  height: auto;
                }
              }
            }
          }
        }
      }
      .second-bar__function-buttons form {
        display: none;
      }
    }
  }
}
</style>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  setup() {},
  data() {
    return {
      isActive: false,
      menuMobile: false,
      menuMobileExtendedBestSellers: false,
      menuMobileExtendedOutlet: false,
      menuMobileExtendedCamisetas: false,
    };
  },
  methods: {
    toggleCart: function () {
      this.isActive = !this.isActive;
    },
    toggleMobileMenu: function () {
      this.menuMobile = !this.menuMobile;
    },
    toggleMenuMobileExtendedBestSellers: function() {
      this.menuMobileExtendedBestSellers = !this.menuMobileExtendedBestSellers
    },
    toggleMenuMobileExtendedOutlet: function() {
      this.menuMobileExtendedOutlet = !this.menuMobileExtendedOutlet
    },
    toggleMenuMobileExtendedCamisetas: function() {
      this.menuMobileExtendedCamisetas = !this.menuMobileExtendedCamisetas
    }
  },
});
</script>
