<template>
    <section id="integration" class="integration">
        <div class="integration__text-block">
            <div class="integration__container">
                <text-block
                        title="Коллаборации & интеграции"
                        :text="text"
                        modifier="no-margin"
                />
            </div>
        </div>
        <div class="integration__slider">
            <swiper :options="swiperOption" style="height: auto">
                <swiper-slide>
                    <div class="integration__slide">
                        <!--todo переделать в цикл-->
                        <div class="integration__row">
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_1.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_2.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_3.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_4.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_5.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_6.png" alt="Изображение">
                            </div>
                        </div>
                    </div>
                </swiper-slide>
                <swiper-slide>
                    <div class="integration__slide">
                        <div class="integration__row">
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_7.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_8.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_9.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_10.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_11.png" alt="Изображение">
                            </div>
                            <div class="integration__item  integration__slide-item">
                                <img src="./../../assets/img/integration/image_12.png" alt="Изображение">
                            </div>
                        </div>
                    </div>
                </swiper-slide>
                <div class="integration__slide-btn  integration__slide-btn--prev" slot="button-prev">
                    <svg viewBox="0 0 15.3 29"><polyline fill="none" stroke="#fbcfc4" stroke-width="1" points="0.5,0.5 14.5,14.5 0.5,28.5"></polyline></svg>
                </div>
                <div class="integration__slide-btn  integration__slide-btn--next" slot="button-next">
                    <svg viewBox="0 0 15.3 29"><polyline fill="none" stroke="#fbcfc4" stroke-width="1" points="0.5,0.5 14.5,14.5 0.5,28.5"></polyline></svg>
                </div>
            </swiper>
        </div>
        <div class="integration__img-block">
            <div class="integration__container">
                <masonry
                    :cols="{default: 4, 1100: 3, 960: 2, 560: 1}"
                    :gutter="10"
                >
                    <div v-for="(image, key) in images" :key="key" class="integration__img">
                        <img :src="image" alt="Изображение">
                    </div>
                </masonry>
            </div>
        </div>
    </section>
</template>

<script>
    import 'swiper/dist/css/swiper.css';
    import {swiper, swiperSlide} from 'vue-awesome-swiper';
    import TextBlock from './../blocks/TextBlock';

    export default {
        name: "Integration",
        components: {
            TextBlock,
            swiper,
            swiperSlide
        },
        data() {
            return {
                text: [
                    'Совместные работы с брендами, селебрити и модными домами — это интересный опыт',
                    'и безусловно полезный для всех участников формат взаимодействия.'
                ],
                swiperOption: {
                    autoHeight: true,
                    spaceBetween: 20,
                    effect: 'fade',
                    loop: true,
                    navigation: {
                        nextEl: '.integration__slide-btn--next',
                        prevEl: '.integration__slide-btn--prev'
                    }
                },
                images: [
                    require('./../../assets/img/masonry/image_1.jpg'),
                    require('./../../assets/img/masonry/image_2.jpg'),
                    require('./../../assets/img/masonry/image_3.jpg'),
                    require('./../../assets/img/masonry/image_4.jpg'),
                    require('./../../assets/img/masonry/image_5.jpg'),
                    require('./../../assets/img/masonry/image_6.jpg'),
                    require('./../../assets/img/masonry/image_7.jpg'),
                    require('./../../assets/img/masonry/image_8.jpg')
                ]
            }

        }
    }
</script>

<style lang="less">
    .integration {
        
        &__text-block {
            padding: 20px 0;
        }

        &__slider {
            background-color: #fff;
        }

        &__container {
            .wrapper();
        }

        &__slide {
            .wrapper();
            background-color: #fff;
        }

        &__row {
            .row-flex();
            justify-content: center;
        }

        &__item {
            .col();
        }

        &__slide-item {
            .size(2);
            .size-md(3.1);
            .size-xs(6);
            align-self: center;
            padding: 20px 0;
        }

        &__slide-btn {
            position: absolute;
            top: 50%;
            width: 60px;
            height: 60px;
            margin-top: -30px;
            z-index: 10;
            cursor: pointer;
            background-color: #000;
            border-radius: 50%;
            transition: background-color .3s;
            border: 0;
            outline: none;

            .xs-block({ width: 24px; height: 24px; });

            svg {
                position: absolute;
                top: 50%;
                margin-top: -14px;
                left: 50%;
                margin-left: -8px;
                width: 16px;
                height: 28px;

                .xs-block({ width: 6px; height: 10px; margin-top: -5px; margin-left: -3px; });
            }

            polyline {
                transition: stroke .3s;
            }

            &:hover {
                background-color: #fbcfc4;
                transition: background-color .3s;

                polyline {
                    stroke: #000;
                    transition: stroke .3s;
                }
            }


            &--prev {
                left: 10px;
                transform: scale(-1);
            }

            &--next {
                right: 10px;
            }
        }

        &__img-block {
            padding-top: 60px;
            padding-bottom: 40px;
        }

        &__img {
            margin-top: 10px;
        }
    }
</style>