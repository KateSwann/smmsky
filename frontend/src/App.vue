<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from '@/components/HelloWorld.vue'
import HeaderMain from '@/components/HeaderMain.vue'
</script>

<template>
    <HeaderMain />

    <section>
        <table style="padding: 200px 0 100px;">
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

        <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

        <div class="wrapper">
            <HelloWorld msg="You did it!" />

            <nav>
                <RouterLink to="/">Home</RouterLink>
                <RouterLink to="/about">About</RouterLink>
            </nav>
        </div>
    </section>

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

ul {
    list-style: none;
}

.screen-reader-text {
    clip: rect(1px,1px,1px,1px);
    word-wrap: normal!important;
    border: 0;
    -webkit-clip-path: inset(50%);
    clip-path: inset(50%);
    height: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
}
</style>
