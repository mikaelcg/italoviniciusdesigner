<template>
    <div class="PageHeader">
        <v-container>
            <div class="PageHeader__content">
                <div class="PageHeader__content-text">
                    <div
                        class="PageHeader__content-text-title"
                        data-aos="fade-right"
                        data-aos-duration="800"
                    >
                        <h1>
                            <slot name="PageHeaderTitle"></slot>
                        </h1>

                        <span>/</span>

                        <h2>
                            <slot name="PageHeaderSubtitle"></slot>
                        </h2>
                    </div>

                    <p
                        class="PageHeader__content-text-description"
                        data-aos="fade-left"
                    >
                        <slot name="PageHeaderDescription"></slot>
                    </p>
                </div>

                <div class="PageHeader__content-image">
                    <slot name="PageHeaderImage"></slot>
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
    props: {},
    data: () => ({
        target: '.PageItem'
    }),
    computed: {
        scrollTarget() {
            const value = this[this.type]
            if (!isNaN(value)) return Number(value)
            else return value
        },
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
            position: relative;
            width: 100%;

            .PageHeader__content-text {
                .PageHeader__content-text-title {
                    display: flex;

                    > h1,
                    h2,
                    span {
                        font-weight: 600;
                        font-size: 14px;
                        line-height: 20px;
                        letter-spacing: 0.1em;
                        font-family: $graphik-regular;
                        letter-spacing: 0.1em;
                    }

                    h1 {
                        color: $grey2;
                    }

                    h2 {
                        color: $grey1;
                    }

                    > span {
                        color: $gold;
                        margin: 0 1rem;
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
                img {
                    max-width: 100%;
                    height: auto;
                }

                @media screen and (max-width: 768px) {
                    display: none;
                }
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
