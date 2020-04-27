<template>
    <div id="PageItemId" class="PageItem">
        <v-container :class="[{ reverse: reverse }]">
            <div :data-aos="getImageAnimation()" class="PageItem__image">
                <slot name="PageItemImage" />
            </div>
            <div
                :data-aos="getTextAnimation()"
                class="PageItem__text"
                data-aos-delay="200"
            >
                <div class="PageItem__text-title">
                    <span>
                        <slot name="PageItemTitle" />
                    </span>

                    <span>/</span>

                    <span>
                        <slot name="PageItemSubtitle" />
                    </span>
                </div>

                <p class="PageItem__text-description">
                    <slot name="PageItemDescription" />
                </p>
                <div class="PageItem__text-action">
                    <nuxt-link :to="to">
                        VER PROJETO
                    </nuxt-link>
                </div>
            </div>
        </v-container>
    </div>
</template>

<script>
export default {
    name: 'IndexPageItem',
    components: {},
    props: {
        reverse: {
            type: Boolean,
            required: true
        },

        to: {
            type: String,
            required: true
        }
    },
    data: () => ({}),
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
    mounted() {},
    methods: {
        getImageAnimation() {
            if (this.reverse) {
                return 'fade-left'
            }

            return 'fade-right'
        },

        getTextAnimation() {
            if (this.reverse) {
                return 'fade-right'
            }

            return 'fade-left'
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';
.PageItem {
    padding: 10rem 0;
    background-color: $white;
    overflow-x: hidden;

    > div {
        display: flex;
        justify-content: space-between;
        align-items: center;

        &.reverse {
            flex-direction: row-reverse;
        }

        .PageItem__image {
            img {
                max-width: 100%;
                height: auto;
            }
        }

        .PageItem__text {
            &-title {
                display: flex;

                span {
                    font-family: $graphik-semibold;
                    font-size: 1.4rem;
                    line-height: 2rem;
                    letter-spacing: 0.1em;

                    &:nth-child(1) {
                        color: $grey1;
                    }

                    &:nth-child(2) {
                        color: $gold;
                        margin: 0 1rem;
                    }

                    &:nth-child(3) {
                        color: $dark;
                    }
                }
            }

            &-description {
                font-family: $graphik-regular;
                font-style: normal;
                font-size: 2.1rem;
                line-height: 3.1rem;
                color: $grey3;
                max-width: 33rem;
                margin: 5rem 0;
            }

            &-action {
                > a {
                    font-family: $opensans-bold;
                    font-style: normal;
                    font-size: 1.2rem;
                    line-height: 147.8%;
                    letter-spacing: 0.1em;
                    color: $grey1;

                    &:hover {
                        transition: all 0.3s;
                        color: $gold;
                    }
                }
            }

            @media screen and (max-width: 768px) {
                width: 100%;
            }
        }

        @media screen and (max-width: 768px) {
            flex-direction: column !important;
            justify-content: center;
            align-items: center;
        }
    }
}
</style>
