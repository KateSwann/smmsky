<script>
import IconSiteLogo from '@/components/icons/IconSiteLogo.vue'

export default {
    name: 'HeaderMain',

    components: {
        IconSiteLogo
    },

    data() {
        return {
            isHeaderScrolled: false
        }
    },

    mounted() {
        window.addEventListener("scroll", this.onScroll);
    },

    beforeDestroy() {
        window.removeEventListener("scroll", this.onScroll);
    },

    methods: {
        onScroll() {
            if (window.pageYOffset < 0) {
                return;
            }

            this.isHeaderScrolled = window.pageYOffset > 0
            console.log(this.isHeaderScrolled);
        }
    },
}
</script>

<template>
    <header class="header-main"
            :class="[isHeaderScrolled ? 'header-main--scrolled' : '']">
        <div class="header-main__content">
            <RouterLink to="/"
                        class="header-main__logo">
                <div class="screen-reader-text">SMMSky</div>
                <IconSiteLogo />
            </RouterLink>

            <nav class="main-nav">
                <ul class="main-nav__list">
                    <li class="main-nav__list-item
                               main-nav__list-item--has-dropdown">
                        <RouterLink to="/"
                                    class="main-nav__list-link">Услуги</RouterLink>

                        <div class="main-nav__dropdown
                                    main-nav-dropdown">
                            <ul class="main-nav-dropdown__list">
                                <li class="main-nav-dropdown__list-item">
                                    <RouterLink to="/"
                                                class="main-nav-dropdown__list-link">Instagram</RouterLink>

                                    <div class="main-nav-dropdown__dropdown-deep
                                                main-nav-dropdown-deep">
                                        <ul class="main-nav-dropdown-deep__list">
                                            <li class="main-nav-dropdown-deep__list-item">
                                                Подписчики
                                                <span class="main-nav-dropdown-deep__list-item-number">от 0.02 ₽/шт</span>
                                            </li>
                                        </ul>
                                    </div>
                                </li>

                                <li class="main-nav-dropdown__list-item">
                                    <RouterLink to="/"
                                                class="main-nav-dropdown__list-link">Telegram</RouterLink>

                                    <div class="main-nav-dropdown__dropdown-deep
                                                main-nav-dropdown-deep">
                                        <ul class="main-nav-dropdown-deep__list">
                                            <li class="main-nav-dropdown-deep__list-item">
                                                Подписчики
                                                <span class="main-nav-dropdown-deep__list-item-number">от 0.02 ₽/шт</span>
                                            </li>
                                        </ul>
                                    </div>
                                </li>
                            </ul>
                        </div>
                    </li>

                    <li class="main-nav__list-item">
                        <RouterLink to="/"
                                    class="main-nav__list-link">Блог</RouterLink>
                    </li>

                    <li class="main-nav__list-item">
                        <RouterLink to="/"
                                    class="main-nav__list-link">Как пользоваться</RouterLink>
                    </li>

                    <li class="main-nav__list-item">
                        <RouterLink to="/"
                                    class="main-nav__list-link">Отзывы</RouterLink>
                    </li>

                    <li class="main-nav__list-item">
                        <RouterLink to="/"
                                    class="main-nav__list-link">FAQ</RouterLink>
                    </li>
                </ul>
            </nav>

            <div class="header-main__buttons-group">
                <div class="button button--secondary">Войти</div>
                <div class="button">Зарегистрироваться</div>
            </div>
        </div>
    </header>
</template>

<style lang="scss">
    .header-main {
        width: 100%;
        display: flex;
        position: absolute;
        z-index: 100;
        transition: all .2s linear;

        &--scrolled {
            background-color: var(--background-color-50);
            position: fixed;
            box-shadow: 0px 10px 20px 0 rgb(0 0 0 / 10%);
        }

        &__logo {
            display: flex;
        }

        @media (max-width: 767px) {}

        @media (min-width: 768px) and (max-width: 1279px) {}

        @media (min-width: 1280px) {
            height: 104px;
            display: flex;
            align-items: center;
            justify-content: center;

            &__content {
                max-width: 1920px;
                padding: 0 56px;
                display: flex;
                flex: 1 1 1808px;
                align-items: center;
                justify-content: center;
            }

            &__logo {
                margin-right: auto;
            }

            &__buttons-group {
                display: flex;
                flex-wrap: nowrap;

                & > * {
                    &:not(:first-child) {
                        margin-left: 16px;
                    }
                }
            }
        }
    }

    .main-nav {
        &__list {}

        &__list-item {
            &--has-dropdown {}
        }

        &__list-link {}

        &__dropdown {}

        @media (max-width: 767px) {}

        @media (min-width: 768px) and (max-width: 1279px) {}

        @media (min-width: 1280px) {
            margin: 1px 145px 0 0;
            letter-spacing: .3px;

            &__list {
                display: flex;
                flex-wrap: nowrap;
            }

            &__list-item {
                position: relative;

                &:not(:last-child) {
                    margin-right: 40px;
                }

                &:hover {
                    .main-nav__dropdown {
                        display: block;
                    }
                }

                &--has-dropdown {
                    .main-nav__list-link {
                        display: flex;
                        align-items: center;
                        flex-wrap: nowrap;

                        &::after {
                            content: "";
                            display: block;
                            width: 12px;
                            height: 8px;
                            margin-left: 11px;
                            background-image: url("data:image/svg+xml,%3Csvg width='12' height='8' viewBox='0 0 12 8' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M10.9997 1.1697C10.8123 0.983448 10.5589 0.878906 10.2947 0.878906C10.0305 0.878906 9.77707 0.983448 9.5897 1.1697L5.9997 4.7097L2.4597 1.1697C2.27234 0.983448 2.01889 0.878906 1.7547 0.878906C1.49052 0.878906 1.23707 0.983448 1.0497 1.1697C0.955976 1.26266 0.881582 1.37326 0.830813 1.49512C0.780044 1.61698 0.753906 1.74769 0.753906 1.8797C0.753906 2.01171 0.780044 2.14242 0.830813 2.26428C0.881582 2.38613 0.955976 2.49674 1.0497 2.5897L5.2897 6.8297C5.38267 6.92343 5.49327 6.99782 5.61513 7.04859C5.73699 7.09936 5.86769 7.1255 5.9997 7.1255C6.13172 7.1255 6.26242 7.09936 6.38428 7.04859C6.50614 6.99782 6.61674 6.92343 6.7097 6.8297L10.9997 2.5897C11.0934 2.49674 11.1678 2.38613 11.2186 2.26428C11.2694 2.14242 11.2955 2.01171 11.2955 1.8797C11.2955 1.74769 11.2694 1.61698 11.2186 1.49512C11.1678 1.37326 11.0934 1.26266 10.9997 1.1697Z' fill='%232D0A54'/%3E%3C/svg%3E%0A");
                        }
                    }
                }
            }

            &__list-link {
                font-size: 16px;
                line-height: 1;
                color: var(--text-color-regular);
                text-decoration: none;
            }

            &__dropdown {
                display: none;
                position: absolute;
                left: 0;
                top: 100%;
            }
        }
    }

    .main-nav-dropdown {
        &__list {}

        &__list-item {}

        &__list-link {}

        &__dropdown-deep {}

        @media (max-width: 767px) {}

        @media (min-width: 768px) and (max-width: 1279px) {}

        @media (min-width: 1280px) {
            $block-padding: 16px;

            width: 187px;
            padding-top: 20px;

            &__list {
                padding: $block-padding 0 $block-padding $block-padding;
                background-color: var(--background-color-50);
                border-radius: 20px;
                box-shadow: 0px 10px 60px 0 rgb(0 0 0 / 10%);
            }

            &__list-item {
                position: relative;
                color: var(--text-color-heavy);

                &:hover {
                    color: var(--text-color-link);

                    .main-nav-dropdown__dropdown-deep {
                        display: block;
                    }
                }

                &:not(:last-child) {
                    padding-bottom: 4px;
                }

                &:not(:first-child) {
                    padding-top: 4px;
                }
            }

            &__list-link {
                display: flex;
                padding-right: $block-padding;
                align-items: center;
                flex-wrap: nowrap;
                font-size: 16px;
                line-height: 24px;
                color: inherit;
                text-decoration: none;

                &::after {
                    content: "";
                    display: block;
                    width: 8px;
                    height: 14px;
                    margin: 0 5px 0 auto;
                    background-repeat: no-repeat;
                    background-image: url("data:image/svg+xml,%3Csvg width='8' height='14' viewBox='0 0 8 14' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M7.54071 6.28955L1.88071 0.639548C1.78775 0.54582 1.67715 0.471426 1.55529 0.420657C1.43343 0.369888 1.30273 0.34375 1.17071 0.34375C1.0387 0.34375 0.907997 0.369888 0.786138 0.420657C0.664278 0.471426 0.553677 0.54582 0.460714 0.639548C0.274463 0.826911 0.169922 1.08036 0.169922 1.34455C0.169922 1.60873 0.274463 1.86219 0.460714 2.04955L5.41071 7.04955L0.460714 11.9995C0.274463 12.1869 0.169922 12.4404 0.169922 12.7045C0.169922 12.9687 0.274463 13.2222 0.460714 13.4095C0.553329 13.504 0.663774 13.5792 0.785649 13.6307C0.907525 13.6822 1.03841 13.709 1.17071 13.7095C1.30302 13.709 1.4339 13.6822 1.55578 13.6307C1.67765 13.5792 1.7881 13.504 1.88071 13.4095L7.54071 7.75955C7.64222 7.66591 7.72323 7.55225 7.77864 7.42576C7.83404 7.29926 7.86265 7.16265 7.86265 7.02455C7.86265 6.88645 7.83404 6.74984 7.77864 6.62334C7.72323 6.49684 7.64222 6.38319 7.54071 6.28955Z' fill='%232D0A54'/%3E%3C/svg%3E%0A");
                }
            }

            &__dropdown-deep {
                display: none;
                position: absolute;
                left: 100%;
                top: 0;
            }
        }
    }

    .main-nav-dropdown-deep {
        &__list {}

        &__list-item {}

        &__list-item-number {}

        @media (max-width: 767px) {}

        @media (min-width: 768px) and (max-width: 1279px) {}

        @media (min-width: 1280px) {
            padding-left: 8px;

            &__list {
                width: 302px;
                padding: 16px;
                background-color: var(--background-color-50);
                border-radius: 20px;
                box-shadow: 0px 10px 60px 0 rgb(0 0 0 / 10%);
            }

            &__list-item {
                display: flex;
                justify-content: space-between;
                line-height: 24px;
                color: var(--text-color-heavy);
                cursor: default;

                &:hover {
                    color: var(--text-color-link);
                }

                &:not(:last-child) {
                    padding-bottom: 4px;
                }

                &:not(:first-child) {
                    padding-top: 4px;
                }
            }

            &__list-item-number {
                font-weight: 500;
            }
        }
    }
</style>
