<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from '@/components/HelloWorld.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>

      <table>
          <thead>
              <tr>
                  <td>.button</td>
                  <td>&lt;button&gt;</td>
              </tr>
          </thead>
          <tbody>
              <tr>
                  <td>
                    <div class="button">Пополнить баланс</div>
                    <div class="button button--secondary">Пополнить баланс</div>
                    <div class="button button--secondary button--disabled">Пополнить баланс</div>
                  </td>
                  <td>
                    <button>Пополнить баланс</button>
                    <button class="button--secondary">Пополнить баланс</button>
                    <button class="button--secondary" disabled>Пополнить баланс</button>
                  </td>
              </tr>

              <tr>
                  <td>
                    <div class="button button--height-md">Пополнить баланс</div>
                    <div class="button button--height-md button--secondary">Пополнить баланс</div>
                    <div class="button button--height-md button--secondary button--disabled">Пополнить баланс</div>
                  </td>
                  <td>
                    <button class="button--height-md">Пополнить баланс</button>
                    <button class="button--height-md button--secondary">Пополнить баланс</button>
                    <button class="button--height-md button--secondary" disabled>Пополнить баланс</button>
                  </td>
              </tr>

              <tr>
                  <td>
                    <div class="button button--height-lg">Пополнить баланс</div>
                    <div class="button button--height-lg button--secondary">Пополнить баланс</div>
                    <div class="button button--height-lg button--secondary button--disabled">Пополнить баланс</div>
                  </td>
                  <td>
                    <button class="button--height-lg">Пополнить баланс</button>
                    <button class="button--height-lg button--secondary">Пополнить баланс</button>
                    <button class="button--height-lg button--secondary" disabled>Пополнить баланс</button>
                  </td>
              </tr>
          </tbody>
      </table>
    </div>
  </header>

  <RouterView />
</template>

<style lang="scss">
@import '@/styles/palette.scss';

html {
    font-family: 'Gilroy';
    font-weight: 400;
    color: var(--text-color-regular);
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  position: relative;
  font-weight: normal;
}

body {
  min-height: 100vh;
  background: var(--background-color-0);
  transition: color 0.5s,
              background-color 0.5s;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
</style>
