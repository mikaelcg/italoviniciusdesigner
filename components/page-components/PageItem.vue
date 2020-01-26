<template>
    <div class="PageItem">
        <v-container :class="[{ reverse: reverse }]">
            <div class="PageItem__image">
                <slot name="PageItemImage"></slot>
            </div>
            <div class="PageItem__text">
                <div class="PageItem__text-title">
                    <span>
                        <slot name="PageItemTitle"></slot>
                    </span>

                    <span>/</span>

                    <span>
                        <slot name="PageItemSubtitle"></slot>
                    </span>
                </div>

                <p class="PageItem__text-description">
                    <slot name="PageItemDescription"></slot>
                </p>
                <div class="PageItem__text-action">
                    <p>Ver projeto</p>
                </div>
            </div>
        </v-container>
    </div>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'

export default {
    name: 'PageItem',
    components: {},
    props: {
        reverse: {
            type: Boolean,
            required: true
        }
    },
    data: () => ({}),
    computed: {},
    watch: {},
    created() {},
    mounted() {},
    methods: {}
}
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';
.PageItem {
    padding: 10rem 0;
    background-color: $white;

    > div {
        display: flex;
        justify-content: space-between;
        align-items: center;

        &.reverse {
            flex-direction: row-reverse;
        }

        .PageItem__text {
            &-title {
                display: flex;

                span {
                    font-weight: 600;
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
                font-style: normal;
                font-weight: normal;
                font-size: 2.1rem;
                line-height: 3.1rem;
                color: $grey3;
                max-width: 33rem;
                margin: 5rem 0;
            }
        }
    }
}
</style>
