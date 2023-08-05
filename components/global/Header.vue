<template>
  <header class="header">
    <div class="first-bar">
      <span class="first-bar__announcment container"
        >10% OFF NO PIX | FRETE GRÁTIS EM COMPRAS ACIMA DE R$ 347</span
      >
    </div>
    <div class="second-bar container">
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
    &__logo {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: flex-start;
      h1 {
        text-indent: -999999px;
        background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iOTUiIGhlaWdodD0iNDciIHZpZXdCb3g9IjAgMCA5NSA0NyIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTIzLjU2IDI0LjhDMjMuNTYgMjUuNDQ4IDIzLjcwNCAyNi4wMiAyMy45OTIgMjYuNTE2QzI0LjI4OCAyNy4wMTIgMjQuNjcyIDI3LjQgMjUuMTQ0IDI3LjY4QzI1LjYxNiAyNy45NiAyNi4xMjggMjguMSAyNi42OCAyOC4xQzI3LjA4IDI4LjEgMjcuNDQ0IDI4LjA0OCAyNy43NzIgMjcuOTQ0QzI4LjEwOCAyNy44NCAyOC40MTIgMjcuNjk2IDI4LjY4NCAyNy41MTJDMjguOTU2IDI3LjMyIDI5LjE4OCAyNy4xIDI5LjM4IDI2Ljg1MlYyOC4xOTZDMjkuMDI4IDI4LjUwOCAyOC42NDQgMjguNzQgMjguMjI4IDI4Ljg5MkMyNy44MTIgMjkuMDQ0IDI3LjI5NiAyOS4xMiAyNi42OCAyOS4xMkMyNi4wOTYgMjkuMTIgMjUuNTQ4IDI5LjAxNiAyNS4wMzYgMjguODA4QzI0LjUzMiAyOC41OTIgMjQuMDg4IDI4LjI5MiAyMy43MDQgMjcuOTA4QzIzLjMyIDI3LjUxNiAyMy4wMiAyNy4wNTYgMjIuODA0IDI2LjUyOEMyMi41ODggMjYgMjIuNDggMjUuNDI0IDIyLjQ4IDI0LjhDMjIuNDggMjQuMTc2IDIyLjU4OCAyMy42IDIyLjgwNCAyMy4wNzJDMjMuMDIgMjIuNTQ0IDIzLjMyIDIyLjA4OCAyMy43MDQgMjEuNzA0QzI0LjA4OCAyMS4zMTIgMjQuNTMyIDIxLjAxMiAyNS4wMzYgMjAuODA0QzI1LjU0OCAyMC41ODggMjYuMDk2IDIwLjQ4IDI2LjY4IDIwLjQ4QzI3LjI5NiAyMC40OCAyNy44MTIgMjAuNTU2IDI4LjIyOCAyMC43MDhDMjguNjQ0IDIwLjg2IDI5LjAyOCAyMS4wOTIgMjkuMzggMjEuNDA0VjIyLjc0OEMyOS4xODggMjIuNSAyOC45NTYgMjIuMjg0IDI4LjY4NCAyMi4xQzI4LjQxMiAyMS45MDggMjguMTA4IDIxLjc2IDI3Ljc3MiAyMS42NTZDMjcuNDQ0IDIxLjU1MiAyNy4wOCAyMS41IDI2LjY4IDIxLjVDMjYuMTI4IDIxLjUgMjUuNjE2IDIxLjY0IDI1LjE0NCAyMS45MkMyNC42NzIgMjIuMiAyNC4yODggMjIuNTg4IDIzLjk5MiAyMy4wODRDMjMuNzA0IDIzLjU3MiAyMy41NiAyNC4xNDQgMjMuNTYgMjQuOFpNMzEuMTE0OCAxOS42NEgzMi4wNzQ4VjI5SDMxLjExNDhWMTkuNjRaTTMzLjQwMDUgMjYuMjRDMzMuNDAwNSAyNS42OCAzMy41MjQ1IDI1LjE4NCAzMy43NzI1IDI0Ljc1MkMzNC4wMjg1IDI0LjMyIDM0LjM3MjUgMjMuOTggMzQuODA0NSAyMy43MzJDMzUuMjM2NSAyMy40ODQgMzUuNzIwNSAyMy4zNiAzNi4yNTY1IDIzLjM2QzM2LjgwMDUgMjMuMzYgMzcuMjg0NSAyMy40ODQgMzcuNzA4NSAyMy43MzJDMzguMTQwNSAyMy45OCAzOC40ODA1IDI0LjMyIDM4LjcyODUgMjQuNzUyQzM4Ljk4NDUgMjUuMTg0IDM5LjExMjUgMjUuNjggMzkuMTEyNSAyNi4yNEMzOS4xMTI1IDI2Ljc5MiAzOC45ODQ1IDI3LjI4OCAzOC43Mjg1IDI3LjcyOEMzOC40ODA1IDI4LjE2IDM4LjE0MDUgMjguNSAzNy43MDg1IDI4Ljc0OEMzNy4yODQ1IDI4Ljk5NiAzNi44MDA1IDI5LjEyIDM2LjI1NjUgMjkuMTJDMzUuNzIwNSAyOS4xMiAzNS4yMzY1IDI4Ljk5NiAzNC44MDQ1IDI4Ljc0OEMzNC4zNzI1IDI4LjUgMzQuMDI4NSAyOC4xNiAzMy43NzI1IDI3LjcyOEMzMy41MjQ1IDI3LjI4OCAzMy40MDA1IDI2Ljc5MiAzMy40MDA1IDI2LjI0Wk0zNC4zNzI1IDI2LjI0QzM0LjM3MjUgMjYuNjI0IDM0LjQ1MjUgMjYuOTY0IDM0LjYxMjUgMjcuMjZDMzQuNzgwNSAyNy41NTYgMzUuMDA0NSAyNy43OTIgMzUuMjg0NSAyNy45NjhDMzUuNTcyNSAyOC4xMzYgMzUuODk2NSAyOC4yMiAzNi4yNTY1IDI4LjIyQzM2LjYxNjUgMjguMjIgMzYuOTM2NSAyOC4xMzYgMzcuMjE2NSAyNy45NjhDMzcuNTA0NSAyNy43OTIgMzcuNzI4NSAyNy41NTYgMzcuODg4NSAyNy4yNkMzOC4wNTY1IDI2Ljk2NCAzOC4xNDA1IDI2LjYyNCAzOC4xNDA1IDI2LjI0QzM4LjE0MDUgMjUuODU2IDM4LjA1NjUgMjUuNTE2IDM3Ljg4ODUgMjUuMjJDMzcuNzI4NSAyNC45MTYgMzcuNTA0NSAyNC42OCAzNy4yMTY1IDI0LjUxMkMzNi45MzY1IDI0LjM0NCAzNi42MTY1IDI0LjI2IDM2LjI1NjUgMjQuMjZDMzUuODk2NSAyNC4yNiAzNS41NzI1IDI0LjM0NCAzNS4yODQ1IDI0LjUxMkMzNS4wMDQ1IDI0LjY4IDM0Ljc4MDUgMjQuOTE2IDM0LjYxMjUgMjUuMjJDMzQuNDUyNSAyNS41MTYgMzQuMzcyNSAyNS44NTYgMzQuMzcyNSAyNi4yNFpNMzkuNTkxMyAyMy40OEg0Mi4zNTEzVjI0LjM4SDM5LjU5MTNWMjMuNDhaTTQwLjQ5MTMgMjEuNTZINDEuNDUxM1YyOUg0MC40OTEzVjIxLjU2Wk00NC4yNzQxIDE5LjY0VjI5SDQzLjMxNDFWMTkuNjRINDQuMjc0MVpNNDYuODU0MSAyNS42NEM0Ni44NTQxIDI1LjE4NCA0Ni43NTQxIDI0Ljg0IDQ2LjU1NDEgMjQuNjA4QzQ2LjM2MjEgMjQuMzc2IDQ2LjA3MDEgMjQuMjYgNDUuNjc4MSAyNC4yNkM0NS4zOTgxIDI0LjI2IDQ1LjE1MDEgMjQuMzIgNDQuOTM0MSAyNC40NEM0NC43MjYxIDI0LjU2IDQ0LjU2MjEgMjQuNzI0IDQ0LjQ0MjEgMjQuOTMyQzQ0LjMzMDEgMjUuMTQgNDQuMjc0MSAyNS4zNzYgNDQuMjc0MSAyNS42NEg0My45NjIxQzQzLjk2MjEgMjUuMiA0NC4wNDYxIDI0LjgxMiA0NC4yMTQxIDI0LjQ3NkM0NC4zODIxIDI0LjEzMiA0NC42MTAxIDIzLjg2IDQ0Ljg5ODEgMjMuNjZDNDUuMTk0MSAyMy40NiA0NS41MzQxIDIzLjM2IDQ1LjkxODEgMjMuMzZDNDYuMzAyMSAyMy4zNiA0Ni42MzQxIDIzLjQ0IDQ2LjkxNDEgMjMuNkM0Ny4yMDIxIDIzLjc2IDQ3LjQyMjEgMjQgNDcuNTc0MSAyNC4zMkM0Ny43MzQxIDI0LjY0IDQ3LjgxNDEgMjUuMDQgNDcuODE0MSAyNS41MlYyOUg0Ni44NTQxVjI1LjY0Wk00OS42MTg4IDIxLjJDNDkuNjE4OCAyMS4wMTYgNDkuNjgyOCAyMC44NiA0OS44MTA4IDIwLjczMkM0OS45NDY4IDIwLjYwNCA1MC4xMDI4IDIwLjU0IDUwLjI3ODggMjAuNTRDNTAuNDYyOCAyMC41NCA1MC42MTg4IDIwLjYwNCA1MC43NDY4IDIwLjczMkM1MC44NzQ4IDIwLjg2IDUwLjkzODggMjEuMDE2IDUwLjkzODggMjEuMkM1MC45Mzg4IDIxLjM3NiA1MC44NzQ4IDIxLjUzMiA1MC43NDY4IDIxLjY2OEM1MC42MTg4IDIxLjc5NiA1MC40NjI4IDIxLjg2IDUwLjI3ODggMjEuODZDNTAuMTAyOCAyMS44NiA0OS45NDY4IDIxLjc5NiA0OS44MTA4IDIxLjY2OEM0OS42ODI4IDIxLjUzMiA0OS42MTg4IDIxLjM3NiA0OS42MTg4IDIxLjJaTTQ5Ljc5ODggMjMuNDhINTAuNzU4OFYyOUg0OS43OTg4VjIzLjQ4Wk01Ni4yNzU5IDI1LjY0QzU2LjI3NTkgMjUuMTg0IDU2LjE3NTkgMjQuODQgNTUuOTc1OSAyNC42MDhDNTUuNzc1OSAyNC4zNzYgNTUuNDgzOSAyNC4yNiA1NS4wOTk5IDI0LjI2QzU0LjgxOTkgMjQuMjYgNTQuNTcxOSAyNC4zMiA1NC4zNTU5IDI0LjQ0QzU0LjE0NzkgMjQuNTUyIDUzLjk4MzkgMjQuNzEyIDUzLjg2MzkgMjQuOTJDNTMuNzUxOSAyNS4xMjggNTMuNjk1OSAyNS4zNjggNTMuNjk1OSAyNS42NFYyOUg1Mi43MzU5VjIzLjQ4SDUzLjY5NTlWMjQuMzQ0QzUzLjg3OTkgMjQuMDA4IDU0LjEwNzkgMjMuNzYgNTQuMzc5OSAyMy42QzU0LjY1OTkgMjMuNDQgNTQuOTc5OSAyMy4zNiA1NS4zMzk5IDIzLjM2QzU1LjkyMzkgMjMuMzYgNTYuMzgzOSAyMy41NTYgNTYuNzE5OSAyMy45NDhDNTcuMDYzOSAyNC4zMzIgNTcuMjM1OSAyNC44NTYgNTcuMjM1OSAyNS41MlYyOUg1Ni4yNzU5VjI1LjY0Wk01OC42Njg2IDI5LjM2SDU5LjY0MDZDNTkuNjQwNiAyOS42MjQgNTkuNzEyNiAyOS44NjggNTkuODU2NiAzMC4wOTJDNjAuMDAwNiAzMC4zMjQgNjAuMjA0NiAzMC41MDggNjAuNDY4NiAzMC42NDRDNjAuNzMyNiAzMC43ODggNjEuMDQ0NiAzMC44NiA2MS40MDQ2IDMwLjg2QzYxLjY4NDYgMzAuODYgNjEuOTYwNiAzMC43OTIgNjIuMjMyNiAzMC42NTZDNjIuNTA0NiAzMC41MiA2Mi43Mjg2IDMwLjMwNCA2Mi45MDQ2IDMwLjAwOEM2My4wODg2IDI5LjcyIDYzLjE4MDYgMjkuMzQ0IDYzLjE4MDYgMjguODhWMjMuNDhINjQuMTQwNlYyOC44OEM2NC4xNDA2IDI5LjUxMiA2NC4wMDg2IDMwLjA0IDYzLjc0NDYgMzAuNDY0QzYzLjQ4MDYgMzAuODk2IDYzLjE0MDYgMzEuMjIgNjIuNzI0NiAzMS40MzZDNjIuMzA4NiAzMS42NTIgNjEuODY4NiAzMS43NiA2MS40MDQ2IDMxLjc2QzYwLjg2ODYgMzEuNzYgNjAuMzkyNiAzMS42NiA1OS45NzY2IDMxLjQ2QzU5LjU2ODYgMzEuMjYgNTkuMjQ4NiAzMC45NzYgNTkuMDE2NiAzMC42MDhDNTguNzg0NiAzMC4yNDggNTguNjY4NiAyOS44MzIgNTguNjY4NiAyOS4zNlpNNTguNTYwNiAyNi4yNEM1OC41NjA2IDI1LjY0IDU4LjY4NDYgMjUuMTI4IDU4LjkzMjYgMjQuNzA0QzU5LjE4MDYgMjQuMjcyIDU5LjUxMjYgMjMuOTQgNTkuOTI4NiAyMy43MDhDNjAuMzQ0NiAyMy40NzYgNjAuODAwNiAyMy4zNiA2MS4yOTY2IDIzLjM2QzYxLjc2MDYgMjMuMzYgNjIuMTY0NiAyMy40NzYgNjIuNTA4NiAyMy43MDhDNjIuODUyNiAyMy45NCA2My4xMjA2IDI0LjI3MiA2My4zMTI2IDI0LjcwNEM2My41MTI2IDI1LjEyOCA2My42MTI2IDI1LjY0IDYzLjYxMjYgMjYuMjRDNjMuNjEyNiAyNi44MzIgNjMuNTEyNiAyNy4zNDQgNjMuMzEyNiAyNy43NzZDNjMuMTIwNiAyOC4yMDggNjIuODUyNiAyOC41NCA2Mi41MDg2IDI4Ljc3MkM2Mi4xNjQ2IDI5LjAwNCA2MS43NjA2IDI5LjEyIDYxLjI5NjYgMjkuMTJDNjAuODAwNiAyOS4xMiA2MC4zNDQ2IDI5LjAwNCA1OS45Mjg2IDI4Ljc3MkM1OS41MTI2IDI4LjU0IDU5LjE4MDYgMjguMjA4IDU4LjkzMjYgMjcuNzc2QzU4LjY4NDYgMjcuMzQ0IDU4LjU2MDYgMjYuODMyIDU4LjU2MDYgMjYuMjRaTTU5LjUzMjYgMjYuMjRDNTkuNTMyNiAyNi42NjQgNTkuNjE2NiAyNy4wMjQgNTkuNzg0NiAyNy4zMkM1OS45NjA2IDI3LjYxNiA2MC4xOTI2IDI3Ljg0IDYwLjQ4MDYgMjcuOTkyQzYwLjc2ODYgMjguMTQ0IDYxLjA4MDYgMjguMjIgNjEuNDE2NiAyOC4yMkM2MS42OTY2IDI4LjIyIDYxLjk3MjYgMjguMTQ0IDYyLjI0NDYgMjcuOTkyQzYyLjUxNjYgMjcuODQgNjIuNzQwNiAyNy42MTYgNjIuOTE2NiAyNy4zMkM2My4wOTI2IDI3LjAyNCA2My4xODA2IDI2LjY2NCA2My4xODA2IDI2LjI0QzYzLjE4MDYgMjUuOTIgNjMuMTI4NiAyNS42NCA2My4wMjQ2IDI1LjRDNjIuOTIwNiAyNS4xNTIgNjIuNzgwNiAyNC45NDQgNjIuNjA0NiAyNC43NzZDNjIuNDM2NiAyNC42MDggNjIuMjQ4NiAyNC40OCA2Mi4wNDA2IDI0LjM5MkM2MS44MzI2IDI0LjMwNCA2MS42MjQ2IDI0LjI2IDYxLjQxNjYgMjQuMjZDNjEuMDgwNiAyNC4yNiA2MC43Njg2IDI0LjMzNiA2MC40ODA2IDI0LjQ4OEM2MC4xOTI2IDI0LjY0IDU5Ljk2MDYgMjQuODY0IDU5Ljc4NDYgMjUuMTZDNTkuNjE2NiAyNS40NTYgNTkuNTMyNiAyNS44MTYgNTkuNTMyNiAyNi4yNFpNNjkuODU0IDI2LjQ1NkM3MC4wNDYgMjYuNzkyIDcwLjI0NiAyNy4wODggNzAuNDU0IDI3LjM0NEM3MC42NyAyNy42IDcwLjkxIDI3LjggNzEuMTc0IDI3Ljk0NEM3MS40MzggMjguMDg4IDcxLjczOCAyOC4xNiA3Mi4wNzQgMjguMTZDNzIuNTIyIDI4LjE2IDcyLjg4MiAyOC4wMzYgNzMuMTU0IDI3Ljc4OEM3My40MjYgMjcuNTQgNzMuNTYyIDI3LjIyNCA3My41NjIgMjYuODRDNzMuNTYyIDI2LjQ2NCA3My40NzQgMjYuMTY0IDczLjI5OCAyNS45NEM3My4xMjIgMjUuNzE2IDcyLjg5IDI1LjUzNiA3Mi42MDIgMjUuNEM3Mi4zMjIgMjUuMjU2IDcyLjAyMiAyNS4xMjggNzEuNzAyIDI1LjAxNkM3MS40OTQgMjQuOTQ0IDcxLjI2MiAyNC44NTIgNzEuMDA2IDI0Ljc0QzcwLjc1IDI0LjYyIDcwLjUwNiAyNC40NzIgNzAuMjc0IDI0LjI5NkM3MC4wNDIgMjQuMTEyIDY5Ljg1IDIzLjg4OCA2OS42OTggMjMuNjI0QzY5LjU1NCAyMy4zNiA2OS40ODIgMjMuMDM2IDY5LjQ4MiAyMi42NTJDNjkuNDgyIDIyLjIzNiA2OS41ODYgMjEuODY0IDY5Ljc5NCAyMS41MzZDNzAuMDAyIDIxLjIwOCA3MC4yOSAyMC45NTIgNzAuNjU4IDIwLjc2OEM3MS4wMjYgMjAuNTc2IDcxLjQ0NiAyMC40OCA3MS45MTggMjAuNDhDNzIuMzc0IDIwLjQ4IDcyLjc3IDIwLjU2OCA3My4xMDYgMjAuNzQ0QzczLjQ1IDIwLjkxMiA3My43NDIgMjEuMTMyIDczLjk4MiAyMS40MDRDNzQuMjIyIDIxLjY2OCA3NC40MSAyMS45NDggNzQuNTQ2IDIyLjI0NEw3My42NyAyMi43NDhDNzMuNTY2IDIyLjU0IDczLjQzNCAyMi4zMzYgNzMuMjc0IDIyLjEzNkM3My4xMTQgMjEuOTM2IDcyLjkxOCAyMS43NzIgNzIuNjg2IDIxLjY0NEM3Mi40NjIgMjEuNTE2IDcyLjE4NiAyMS40NTIgNzEuODU4IDIxLjQ1MkM3MS40MDIgMjEuNDUyIDcxLjA3IDIxLjU2NCA3MC44NjIgMjEuNzg4QzcwLjY1NCAyMi4wMDQgNzAuNTUgMjIuMjQ4IDcwLjU1IDIyLjUyQzcwLjU1IDIyLjc1MiA3MC42MSAyMi45NjggNzAuNzMgMjMuMTY4QzcwLjg1IDIzLjM2IDcxLjA1IDIzLjU0NCA3MS4zMyAyMy43MkM3MS42MTggMjMuODg4IDcyLjAwNiAyNC4wNTYgNzIuNDk0IDI0LjIyNEM3Mi43MTggMjQuMzA0IDcyLjk1NCAyNC40MDggNzMuMjAyIDI0LjUzNkM3My40NSAyNC42NjQgNzMuNjc4IDI0LjgyOCA3My44ODYgMjUuMDI4Qzc0LjEwMiAyNS4yMiA3NC4yNzggMjUuNDU2IDc0LjQxNCAyNS43MzZDNzQuNTUgMjYuMDA4IDc0LjYxOCAyNi4zMzYgNzQuNjE4IDI2LjcyQzc0LjYxOCAyNy4wODggNzQuNTQ2IDI3LjQyIDc0LjQwMiAyNy43MTZDNzQuMjY2IDI4LjAxMiA3NC4wNzQgMjguMjY0IDczLjgyNiAyOC40NzJDNzMuNTg2IDI4LjY4IDczLjMxIDI4Ljg0IDcyLjk5OCAyOC45NTJDNzIuNjk0IDI5LjA2NCA3Mi4zNzQgMjkuMTIgNzIuMDM4IDI5LjEyQzcxLjU4MiAyOS4xMiA3MS4xNTggMjkuMDI0IDcwLjc2NiAyOC44MzJDNzAuMzgyIDI4LjYzMiA3MC4wNDIgMjguMzcyIDY5Ljc0NiAyOC4wNTJDNjkuNDU4IDI3LjcyNCA2OS4yMjIgMjcuMzc2IDY5LjAzOCAyNy4wMDhMNjkuODU0IDI2LjQ1NlpNNzUuMjE2MyAyMy40OEg3Ny45NzYzVjI0LjM4SDc1LjIxNjNWMjMuNDhaTTc2LjExNjMgMjEuNTZINzcuMDc2M1YyOUg3Ni4xMTYzVjIxLjU2Wk03OC40NTkxIDI2LjI0Qzc4LjQ1OTEgMjUuNjggNzguNTgzMSAyNS4xODQgNzguODMxMSAyNC43NTJDNzkuMDg3MSAyNC4zMiA3OS40MzExIDIzLjk4IDc5Ljg2MzEgMjMuNzMyQzgwLjI5NTEgMjMuNDg0IDgwLjc3OTEgMjMuMzYgODEuMzE1MSAyMy4zNkM4MS44NTkxIDIzLjM2IDgyLjM0MzEgMjMuNDg0IDgyLjc2NzEgMjMuNzMyQzgzLjE5OTEgMjMuOTggODMuNTM5MSAyNC4zMiA4My43ODcxIDI0Ljc1MkM4NC4wNDMxIDI1LjE4NCA4NC4xNzExIDI1LjY4IDg0LjE3MTEgMjYuMjRDODQuMTcxMSAyNi43OTIgODQuMDQzMSAyNy4yODggODMuNzg3MSAyNy43MjhDODMuNTM5MSAyOC4xNiA4My4xOTkxIDI4LjUgODIuNzY3MSAyOC43NDhDODIuMzQzMSAyOC45OTYgODEuODU5MSAyOS4xMiA4MS4zMTUxIDI5LjEyQzgwLjc3OTEgMjkuMTIgODAuMjk1MSAyOC45OTYgNzkuODYzMSAyOC43NDhDNzkuNDMxMSAyOC41IDc5LjA4NzEgMjguMTYgNzguODMxMSAyNy43MjhDNzguNTgzMSAyNy4yODggNzguNDU5MSAyNi43OTIgNzguNDU5MSAyNi4yNFpNNzkuNDMxMSAyNi4yNEM3OS40MzExIDI2LjYyNCA3OS41MTExIDI2Ljk2NCA3OS42NzExIDI3LjI2Qzc5LjgzOTEgMjcuNTU2IDgwLjA2MzEgMjcuNzkyIDgwLjM0MzEgMjcuOTY4QzgwLjYzMTEgMjguMTM2IDgwLjk1NTEgMjguMjIgODEuMzE1MSAyOC4yMkM4MS42NzUxIDI4LjIyIDgxLjk5NTEgMjguMTM2IDgyLjI3NTEgMjcuOTY4QzgyLjU2MzEgMjcuNzkyIDgyLjc4NzEgMjcuNTU2IDgyLjk0NzEgMjcuMjZDODMuMTE1MSAyNi45NjQgODMuMTk5MSAyNi42MjQgODMuMTk5MSAyNi4yNEM4My4xOTkxIDI1Ljg1NiA4My4xMTUxIDI1LjUxNiA4Mi45NDcxIDI1LjIyQzgyLjc4NzEgMjQuOTE2IDgyLjU2MzEgMjQuNjggODIuMjc1MSAyNC41MTJDODEuOTk1MSAyNC4zNDQgODEuNjc1MSAyNC4yNiA4MS4zMTUxIDI0LjI2QzgwLjk1NTEgMjQuMjYgODAuNjMxMSAyNC4zNDQgODAuMzQzMSAyNC41MTJDODAuMDYzMSAyNC42OCA3OS44MzkxIDI0LjkxNiA3OS42NzExIDI1LjIyQzc5LjUxMTEgMjUuNTE2IDc5LjQzMTEgMjUuODU2IDc5LjQzMTEgMjYuMjRaTTg2LjQ0OTggMjMuNDhWMjlIODUuNDg5OFYyMy40OEg4Ni40NDk4Wk04OC4xMTc4IDI0LjUzNkM4Ny45ODk4IDI0LjQ0IDg3Ljg3MzggMjQuMzcyIDg3Ljc2OTggMjQuMzMyQzg3LjY2NTggMjQuMjg0IDg3LjUzMzggMjQuMjYgODcuMzczOCAyNC4yNkM4Ny4xMzM4IDI0LjI2IDg2Ljk0NTggMjQuMzIgODYuODA5OCAyNC40NEM4Ni42NzM4IDI0LjU2IDg2LjU3NzggMjQuNzI0IDg2LjUyMTggMjQuOTMyQzg2LjQ3MzggMjUuMTQgODYuNDQ5OCAyNS4zNzYgODYuNDQ5OCAyNS42NEg4Ni4wMTc4Qzg2LjAxNzggMjUuMiA4Ni4wOTM4IDI0LjgxMiA4Ni4yNDU4IDI0LjQ3NkM4Ni40MDU4IDI0LjEzMiA4Ni42MDk4IDIzLjg2IDg2Ljg1NzggMjMuNjZDODcuMTA1OCAyMy40NiA4Ny4zNTc4IDIzLjM2IDg3LjYxMzggMjMuMzZDODcuODEzOCAyMy4zNiA4Ny45OTc4IDIzLjM4OCA4OC4xNjU4IDIzLjQ0NEM4OC4zNDE4IDIzLjQ5MiA4OC41MDE4IDIzLjU5MiA4OC42NDU4IDIzLjc0NEw4OC4xMTc4IDI0LjUzNlpNOTEuNTYzMyAyOS4xMkM5MS4wNTEzIDI5LjEyIDkwLjU5NTMgMjkgOTAuMTk1MyAyOC43NkM4OS44MDMzIDI4LjUxMiA4OS40OTUzIDI4LjE3MiA4OS4yNzEzIDI3Ljc0Qzg5LjA1NTMgMjcuMzA4IDg4Ljk0NzMgMjYuODA4IDg4Ljk0NzMgMjYuMjRDODguOTQ3MyAyNS42NjQgODkuMDU5MyAyNS4xNiA4OS4yODMzIDI0LjcyOEM4OS41MTUzIDI0LjI5NiA4OS44MzUzIDIzLjk2IDkwLjI0MzMgMjMuNzJDOTAuNjU5MyAyMy40OCA5MS4xMzkzIDIzLjM2IDkxLjY4MzMgMjMuMzZDOTIuMjI3MyAyMy4zNiA5Mi42OTEzIDIzLjQ3NiA5My4wNzUzIDIzLjcwOEM5My40NjczIDIzLjkzMiA5My43NjczIDI0LjI1NiA5My45NzUzIDI0LjY4Qzk0LjE4MzMgMjUuMTA0IDk0LjI4NzMgMjUuNjA4IDk0LjI4NzMgMjYuMTkyQzk0LjI4NzMgMjYuMjQ4IDk0LjI4MzMgMjYuMzA4IDk0LjI3NTMgMjYuMzcyQzk0LjI3NTMgMjYuNDI4IDk0LjI3NTMgMjYuNDY0IDk0LjI3NTMgMjYuNDhIODkuNTU5M1YyNS42NjRIOTMuNTE5M0w5My4xMzUzIDI2LjIxNkM5My4xNTkzIDI2LjE3NiA5My4xODMzIDI2LjExNiA5My4yMDczIDI2LjAzNkM5My4yMzEzIDI1Ljk0OCA5My4yNDMzIDI1Ljg3NiA5My4yNDMzIDI1LjgyQzkzLjI0MzMgMjUuNDkyIDkzLjE3NTMgMjUuMjA4IDkzLjAzOTMgMjQuOTY4QzkyLjkxMTMgMjQuNzI4IDkyLjczMTMgMjQuNTQgOTIuNDk5MyAyNC40MDRDOTIuMjY3MyAyNC4yNjggOTEuOTk1MyAyNC4yIDkxLjY4MzMgMjQuMkM5MS4zMTUzIDI0LjIgOTAuOTk5MyAyNC4yOCA5MC43MzUzIDI0LjQ0QzkwLjQ3OTMgMjQuNTkyIDkwLjI3OTMgMjQuODE2IDkwLjEzNTMgMjUuMTEyQzg5Ljk5OTMgMjUuNCA4OS45MjczIDI1Ljc1NiA4OS45MTkzIDI2LjE4Qzg5LjkxOTMgMjYuNjEyIDg5Ljk4NzMgMjYuOTggOTAuMTIzMyAyNy4yODRDOTAuMjU5MyAyNy41ODggOTAuNDU5MyAyNy44MiA5MC43MjMzIDI3Ljk4QzkwLjk4NzMgMjguMTQgOTEuMzA3MyAyOC4yMiA5MS42ODMzIDI4LjIyQzkyLjA1OTMgMjguMjIgOTIuMzkxMyAyOC4xNCA5Mi42NzkzIDI3Ljk4QzkyLjk2NzMgMjcuODEyIDkzLjIxMTMgMjcuNTYgOTMuNDExMyAyNy4yMjRMOTQuMTkxMyAyNy43MTZDOTMuOTAzMyAyOC4xOCA5My41MzkzIDI4LjUzMiA5My4wOTkzIDI4Ljc3MkM5Mi42NjczIDI5LjAwNCA5Mi4xNTUzIDI5LjEyIDkxLjU2MzMgMjkuMTJaIiBmaWxsPSIjODAxMUE3Ii8+CjxwYXRoIGQ9Ik04LjMyIDIzLjZDOC4zMiAyNy4wNTYgOS4wODggMzAuMTA2NyAxMC42MjQgMzIuNzUyQzEyLjIwMjcgMzUuMzk3MyAxNC4yNTA3IDM3LjQ2NjcgMTYuNzY4IDM4Ljk2QzE5LjI4NTMgNDAuNDUzMyAyMi4wMTYgNDEuMiAyNC45NiA0MS4yQzI3LjA5MzMgNDEuMiAyOS4wMzQ3IDQwLjkyMjcgMzAuNzg0IDQwLjM2OEMzMi41NzYgMzkuODEzMyAzNC4xOTczIDM5LjA0NTMgMzUuNjQ4IDM4LjA2NEMzNy4wOTg3IDM3LjA0IDM4LjMzNiAzNS44NjY3IDM5LjM2IDM0LjU0NFY0MS43MTJDMzcuNDgyNyA0My4zNzYgMzUuNDM0NyA0NC42MTMzIDMzLjIxNiA0NS40MjRDMzAuOTk3MyA0Ni4yMzQ3IDI4LjI0NTMgNDYuNjQgMjQuOTYgNDYuNjRDMjEuODQ1MyA0Ni42NCAxOC45MjI3IDQ2LjA4NTMgMTYuMTkyIDQ0Ljk3NkMxMy41MDQgNDMuODI0IDExLjEzNiA0Mi4yMjQgOS4wODggNDAuMTc2QzcuMDQgMzguMDg1MyA1LjQ0IDM1LjYzMiA0LjI4OCAzMi44MTZDMy4xMzYgMzAgMi41NiAyNi45MjggMi41NiAyMy42QzIuNTYgMjAuMjcyIDMuMTM2IDE3LjIgNC4yODggMTQuMzg0QzUuNDQgMTEuNTY4IDcuMDQgOS4xMzYgOS4wODggNy4wODhDMTEuMTM2IDQuOTk3MzMgMTMuNTA0IDMuMzk3MzMgMTYuMTkyIDIuMjg4QzE4LjkyMjcgMS4xMzYgMjEuODQ1MyAwLjU1OTk5OCAyNC45NiAwLjU1OTk5OEMyOC4yNDUzIDAuNTU5OTk4IDMwLjk5NzMgMC45NjUzMzEgMzMuMjE2IDEuNzc2QzM1LjQzNDcgMi41ODY2NiAzNy40ODI3IDMuODI0IDM5LjM2IDUuNDg4VjEyLjY1NkMzOC4zMzYgMTEuMzMzMyAzNy4wOTg3IDEwLjE4MTMgMzUuNjQ4IDkuMkMzNC4xOTczIDguMTc2IDMyLjU3NiA3LjM4NjY2IDMwLjc4NCA2LjgzMkMyOS4wMzQ3IDYuMjc3MzMgMjcuMDkzMyA2IDI0Ljk2IDZDMjIuMDE2IDYgMTkuMjg1MyA2Ljc0NjY3IDE2Ljc2OCA4LjI0QzE0LjI1MDcgOS43MzMzMyAxMi4yMDI3IDExLjgwMjcgMTAuNjI0IDE0LjQ0OEM5LjA4OCAxNy4wNTA3IDguMzIgMjAuMTAxMyA4LjMyIDIzLjZaIiBmaWxsPSJ1cmwoI3BhaW50MF9saW5lYXJfMV81KSIvPgo8ZGVmcz4KPGxpbmVhckdyYWRpZW50IGlkPSJwYWludDBfbGluZWFyXzFfNSIgeDE9IjgxLjUiIHkxPSIyNCIgeDI9Ii0zMiIgeTI9IjI0IiBncmFkaWVudFVuaXRzPSJ1c2VyU3BhY2VPblVzZSI+CjxzdG9wIHN0b3AtY29sb3I9IiM4MjUwRUMiLz4KPHN0b3Agb2Zmc2V0PSIxIiBzdG9wLWNvbG9yPSIjQ0JDQkNCIiBzdG9wLW9wYWNpdHk9IjAiLz4KPC9saW5lYXJHcmFkaWVudD4KPC9kZWZzPgo8L3N2Zz4K)
          no-repeat center;
        display: inline-block;
        background-size: 100%;
        width: 150px;
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
            font-weight: 500;
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
      grid-template-columns: 180px 1fr 1fr !important;
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
    };
  },
  methods: {
    toggleCart: function () {
      this.isActive = !this.isActive;
    },
  },
});
</script>
