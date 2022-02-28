<script>
import IconSiteLogo from '@/components/icons/IconSiteLogo.vue'

export default {
    name: 'HeaderMain',

    components: {
        IconSiteLogo
    },
}
</script>

<template>
    <footer class="footer">
        <div class="footer__content">
            <div class="footer__main-group">
                <RouterLink to="/"
                            class="footer__logo">
                    <div class="screen-reader-text">SMMSky</div>
                    <IconSiteLogo />
                </RouterLink>

                <nav class="footer-nav
                            footer-nav--main">
                    <ul class="footer-nav__list">
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Услуги</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Блог</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Как пользоваться</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Отзывы</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">FAQ</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Блог</RouterLink>
                        </li>
                    </ul>
                </nav>

                <section class="section-email-us">
                    <h3 class="footer__section-title">Возникли вопросы?</h3>
                    <p class="footer__section-subtitle">Напишите нам, мы все решим</p>
                </section>

                <nav class="footer-nav
                            footer-nav--secondary">
                    <ul class="footer-nav__list">
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Instagram</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Telegram</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Вконтакте</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Youtube</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Twitch</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Тик Ток</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Facebook</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Twitter</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Одноклассники</RouterLink>
                        </li>
                        <li class="footer-nav__list-item">
                            <RouterLink to="/"
                                        class="footer-nav__list-item-link">Яндекс.Дзен</RouterLink>
                        </li>
                    </ul>
                </nav>
            </div>

            <div class="footer__secondary-group">
                <section class="section-blog">
                    <h3 class="footer__section-title">Подписка на блог</h3>
                </section>

                <section class="section-cabinet">
                    <h3 class="footer__section-title">Личный кабинет</h3>

                    <div class="header-main-mobile-dropdown__buttons-group">
                        <div class="button
                                    button--height-lg">Зарегистрироваться</div>
                        <div class="button">Войти</div>
                    </div>
                </section>
            </div>
        </div>
    </footer>
</template>

<style lang="scss">
    .footer {
        background-color: var(--background-color-100);

        &__content {
            max-width: 1575px;
            margin: 0 auto;
        }

        &__logo {
            display: flex;
        }

        &__section-title {
            margin-bottom: 16px;
            font-family: 'Gilroy';
            font-weight: 500;
            color: var(--text-color-heavy);
        }

        &__section-subtitle {
            margin: 0 0 16px;
            font: 16px/24px 'Gilroy';
            letter-spacing: .3px;
            color: var(--text-color-regular);
        }

        .footer-nav {
            &__list {
                display: flex;
                flex-flow: column nowrap;
            }

            &__list-item-link {
                font: 400 16px/24px 'Gilroy';
                letter-spacing: .3px;
            }
        }

        @media (max-width: 1279px) {
            &__content {
                max-width: 320px;
                padding: 40px 10px;
                margin: 0 auto;
            }

            &__logo {
                position: absolute;
            }

            &__section-title {
                font-size: 24px;
                line-height: 32px;
            }

            &__main-group {
                display: flex;
                flex-wrap: wrap;
                position: relative;
            }

            .footer-nav {
                &--main {
                    order: 1;
                    margin-top: 160px;
                    flex: 1 50%;
                }

                &--secondary {
                    display: flex;
                    order: 2;
                    flex: 1 50%;

                    .footer-nav__list {
                        margin-left: auto;
                    }
                }

                &__list-item {
                    &:not(:last-child) {
                        margin-bottom: 16px;
                    }
                }
            }

            .section-email-us {
                margin: 24px 0;
                display: flex;
                flex-direction: column;
                align-items: center;
                flex: 1 0 100%;
                order: 3;
            }

            .section-blog {
                margin-bottom: 24px;
                display: flex;
                flex-direction: column;
                align-items: center;
            }

            .section-cabinet {
                display: flex;
                flex-direction: column;
                align-items: center;
            }
        }

        @media (min-width: 1280px) {
            padding: 80px 20px 87px;

            &__content {
                display: flex;
                flex-wrap: nowrap;
                justify-content: space-between;
            }

            &__logo {
                width: 247px;
                margin-bottom: 300px;
            }

            &__section-title {
                font-size: 36px;
                line-height: 44px;
            }

            &__main-group {
                column-count: 3;
                column-gap: 68px;

                & > * {
                    break-inside: avoid-column;
                }
            }

            .footer-nav {
                &__list-item {
                    &:not(:last-child) {
                        margin-bottom: 24px;
                    }
                }
            }

            .section-email-us {
                margin-top: 37px;
            }

            .section-blog {
                &::after {
                    content: '';
                    display: block;
                    width: 297px;
                    height: 171px;
                    margin: 47px 0 15px 36px;
                    background-image: url("data:image/svg+xml,%3Csvg width='296' height='173' viewBox='0 0 296 173' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1 37.3254C55.9623 14.3807 170.329 -21.2476 188.1 19.7962C210.312 71.101 126.587 197.652 81.3076 128.391C36.0278 59.1295 208.604 -24.6682 258.582 49.2961C298.565 108.468 297.739 155.753 292.328 172' stroke='%231B1BE8'/%3E%3C/svg%3E%0A");
                    background-repeat: no-repeat;
                }
            }
        }
    }
</style>
