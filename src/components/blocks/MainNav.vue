<template>
    <nav class="main-nav">
        <ul class="main-nav__list">
            <li class="main-nav__item">
                <router-link to="/portfolio" class="main-nav__link" v-scroll-to="'#portfolio'">Портфолио</router-link>
            </li>
            <li class="main-nav__item">
                <router-link to="/beauty-academy" class="main-nav__link" v-scroll-to="'#beauty-academy'">Обучение</router-link>
            </li>
            <li class="main-nav__item">
                <router-link to="/integration" class="main-nav__link" v-scroll-to="'#integration'">Коллаборации</router-link>
            </li>
            <li class="main-nav__item">
                <router-link to="/biography" class="main-nav__link">Биография</router-link>
            </li>
            <li class="main-nav__item">
                <router-link to="/feedback" class="main-nav__link" v-scroll-to="'#feedback'">Сотрудничество</router-link>
            </li>
        </ul>
    </nav>
</template>

<script>
    export default {
        name: "MainNav"
    }
</script>

<style lang="less">
    .main-nav {
        &__list {
            display: flex;
            justify-content: center;
            align-items: center;
            padding-top: 10px;
            .md-block({ flex-direction: column; padding-top: 10px; });
        }
        &__item {
            margin: 10px 15px;
            cursor: pointer;
        }
        &__link {
            position: relative;
            font-size: 14px;
            font-weight: bold;
            color: #000;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            transition: color 0.3s ease-in-out;

            &::after {
                content: '';
                position: absolute;
                left: 0;
                bottom: 10%;
                opacity: 0;
                width: 100%;
                height: 2px;
                border-bottom: 0 solid #fbcfc4;
                box-shadow: inset 0px -1px 0px 0px #fbcfc4;
                transition: all 0.3s ease;
            }

            &:hover {
                color: #fbcfc4;
                text-decoration: none;
                transition: color 0.3s ease-in-out;

                &::after {
                    opacity: 1;
                }
            }
        }
    }
    .router-link-active, .router-link-exact-active {
        opacity: .8;
        color: #545454 !important;
        text-decoration: none;

        &::after {
            display: none;
        }

        &:focus {
            text-decoration: none;
        }

        &:hover {
            color: #545454 !important;
        }

    }
</style>