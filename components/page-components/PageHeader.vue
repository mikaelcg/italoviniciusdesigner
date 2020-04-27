<template>
    <div
        :class="[
            'PageHeader',
            { backgroundColorDarkGrey: backgroundColorDarkGrey },
            { backgroundColorGrey: backgroundColorGrey }
        ]"
    >
        <v-container>
            <div class="PageHeader__content">
                <div class="PageHeader__content-text">
                    <div
                        class="PageHeader__content-text-title"
                        data-aos="fade-right"
                        data-aos-duration="800"
                    >
                        <div class="Text__title">
                            <h1>
                                <slot name="PageHeaderTitle" />
                            </h1>

                            <span>/</span>

                            <h2>
                                <slot name="PageHeaderSubtitle" />
                            </h2>
                        </div>

                        <div class="Text__year">
                            <span>ANO</span>
                            <span>/</span>
                            <span>
                                <slot name="PageHeaderYear" />
                            </span>
                        </div>
                    </div>

                    <p
                        class="PageHeader__content-text-description"
                        data-aos="fade-left"
                    >
                        <slot name="PageHeaderDescription" />
                    </p>
                </div>

                <div
                    :class="[
                        'PageHeader__content-image',
                        { novoSite: novoSite }
                    ]"
                >
                    <slot name="PageHeaderImage" />
                </div>
            </div>

            <div
                @click="$vuetify.goTo(target, scrollOptions)"
                class="PageHeader__icon"
                data-aos="fade-down"
            >
                <v-icon>mdi-arrow-down</v-icon>
            </div>
        </v-container>
    </div>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'
import AOS from 'aos'
export default {
    name: 'PageHeader',
    components: {},
    props: {
        backgroundColorDarkGrey: {
            type: Boolean
        },
        backgroundColorGrey: {
            type: Boolean
        },
        novoSite: {
            type: Boolean
        }
    },
    data: () => ({
        target: '.PageItemTextContent'
    }),
    computed: {
        scrollOptions() {
            return {
                duration: 1000,
                offset: 0,
                easing: 'easeInOutCubic'
            }
        }
    },
    watch: {},
    created() {},
    mounted() {
        AOS.refreshHard()
    },
    methods: {}
}
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.PageHeader {
    background: $dark;

    > div {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-start;

        .PageHeader__content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            // position: relative;
            width: 100%;
            min-height: 63rem;

            .PageHeader__content-text {
                .PageHeader__content-text-title {
                    display: flex;
                    align-items: flex-end;

                    .Text__title {
                        display: flex;

                        > h1,
                        h2,
                        span {
                            font-weight: 600;
                            font-size: 1.4rem;
                            line-height: 2rem;
                            letter-spacing: 0.1em;
                            font-family: $graphik-regular;
                            letter-spacing: 0.1em;
                        }

                        h1 {
                            color: $grey1;
                        }

                        h2 {
                            color: $grey2;
                        }

                        > span {
                            color: $gold;
                            margin: 0 1rem;
                        }
                    }

                    .Text__year {
                        display: flex;
                        margin-left: 4rem;

                        span {
                            font-weight: 600;
                            font-size: 1.4rem;
                            line-height: 2rem;
                            letter-spacing: 0.1em;
                            font-family: $graphik-regular;
                            letter-spacing: 0.1em;

                            &:nth-child(1) {
                                color: $grey1;
                            }

                            &:nth-child(3) {
                                color: $grey2;
                            }

                            &:nth-child(2) {
                                color: $gold;
                                margin: 0 1rem;
                            }
                        }
                    }

                    @media screen and (max-width: 768px) {
                        display: flex;
                        flex-direction: column;
                        justify-content: flex-start;
                        align-items: flex-start;

                        .Text__year {
                            margin-left: 0;
                            margin-top: 2rem;
                        }
                    }
                }

                .PageHeader__content-text-description {
                    font-family: $acta-display-bold;
                    font-size: 36px;
                    line-height: 54px;
                    color: $grey2;
                    max-width: 673px;
                    margin: 5rem 0;
                }
            }

            .PageHeader__content-image {
                position: absolute;
                right: 0;

                img {
                    max-width: 100%;
                    height: auto;
                }

                &.novoSite {
                    position: relative;
                    top: 10rem;
                }

                @media screen and (max-width: 768px) {
                    display: none;
                }
            }

            @media screen and (max-width: 768px) {
                min-height: 0;
            }
        }

        .PageHeader__icon {
            > i {
                color: $gold !important;
                font-size: 3.4rem;
                -webkit-animation: slide-bottom 0.5s ease-in-out both infinite
                    alternate 1s;
                animation: slide-bottom 0.5s ease-in-out both infinite alternate
                    1s;
                cursor: pointer;
                margin-bottom: 5rem;
            }
        }
    }

    &.backgroundColorDarkGrey {
        background: #ebebeb;

        > div {
            .PageHeader__content {
                .PageHeader__content-text {
                    .PageHeader__content-text-title {
                        .Text__title {
                            h2 {
                                color: $dark;
                            }
                        }

                        .Text__year {
                            span {
                                &:nth-child(3) {
                                    color: $dark;
                                }
                            }
                        }
                    }

                    .PageHeader__content-text-description {
                        color: $dark;
                    }
                }
            }
        }
    }

    &.backgroundColorGrey {
        background: #f1f1f1;

        > div {
            .PageHeader__content {
                .PageHeader__content-text {
                    .PageHeader__content-text-title {
                        .Text__title {
                            h2 {
                                color: $dark;
                            }
                        }

                        .Text__year {
                            span {
                                &:nth-child(3) {
                                    color: $dark;
                                }
                            }
                        }
                    }

                    .PageHeader__content-text-description {
                        color: $dark;
                    }
                }
            }
        }
    }
}

@-webkit-keyframes slide-bottom {
    0% {
        -webkit-transform: translateY(0);
        transform: translateY(0);
    }
    100% {
        -webkit-transform: translateY(10px);
        transform: translateY(10px);
    }
}

@keyframes slide-bottom {
    0% {
        -webkit-transform: translateY(0);
        transform: translateY(0);
    }
    100% {
        -webkit-transform: translateY(10px);
        transform: translateY(10px);
    }
}
</style>
