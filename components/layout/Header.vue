<template>
    <header
        :class="[
            'Header',
            { fixed: fixed },
            { white: white },
            { 'novo-menu': this.$route.name === 'ummense-novo-menu' },
            { 'novo-site': this.$route.name === 'ummense-novo-site' }
        ]"
    >
        <v-container>
            <a
                :class="[
                    {
                        active:
                            activeOption === 'home' &&
                            this.$route.name === 'index'
                    }
                ]"
                @click="handleMenuClick('#PageHeaderId')"
                href="javascript:void(0)"
                >INÍCIO</a
            >
            <a
                :class="[
                    {
                        active:
                            activeOption === 'work' &&
                            this.$route.name === 'index'
                    }
                ]"
                @click="handleMenuClick('#PageItemId')"
                href="javascript:void(0)"
                >TRABALHOS</a
            >
            <a
                :class="[
                    {
                        active:
                            activeOption === 'about' &&
                            this.$route.name === 'index'
                    }
                ]"
                @click="$vuetify.goTo('.About', scrollOptions)"
                href="javascript:void(0)"
                >SOBRE</a
            >
        </v-container>
    </header>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'

export default {
    name: 'Header',
    components: {},
    props: {
        fixed: {
            type: Boolean,
            required: false,
            default: false
        },
        white: {
            type: Boolean,
            required: false,
            default: false
        },
        activeOption: {
            type: String,
            required: false,
            default: 'home'
        }
    },
    data: () => ({}),
    computed: {
        scrollOptions() {
            return {
                duration: 1000,
                offset: 0,
                easing: 'easeInOutCubic',
                behavior: 'smooth'
            }
        }
    },
    watch: {},
    created() {},
    mounted() {},
    methods: {
        handleMenuClick(goTo) {
            if (this.$route.name === 'index') {
                this.$vuetify.goTo(goTo, this.scrollOptions)
            } else {
                this.$router.push({ name: 'index' })
                setTimeout(() => {
                    this.$vuetify.goTo(goTo, this.scrollOptions)
                }, 1000)
            }
        }
    }
}
</script>

<style lang="scss" scoped>
// @import '@/assets/variables.scss';

.Header {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    height: 8rem;
    background-color: $dark;
    position: relative;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 10;

    &.fixed {
        position: fixed;
    }

    &.white {
        background-color: $white;

        a {
            color: $grey3;

            &:hover,
            &.active {
                color: $dark;

                &:before {
                    transform: translateX(0);
                }
            }
        }
    }

    a {
        position: relative;
        margin-right: 100px;
        font-size: 14px;
        letter-spacing: 0.1em;
        font-family: $graphik-semibold;
        text-transform: uppercase;
        display: inline-block;
        overflow: hidden;
        transition: all 0.5s ease;
        color: $grey1;

        &:before {
            content: '';
            position: absolute;
            transition: transform 0.5s ease;
            left: -1px;
            bottom: 0;
            width: 100%;
            height: 2px;
            background: #979724;
            transform: translateX(-100%);
        }

        &:hover,
        &.active {
            color: $grey2;

            &:before {
                transform: translateX(0);
            }
        }
    }

    &.novo-menu {
        background-color: #ebebeb;

        a {
            &:hover,
            &.active {
                color: $dark;

                &:before {
                    transform: translateX(0);
                }
            }
        }
    }

    &.novo-site {
        background-color: #f1f1f1;

        a {
            &:hover,
            &.active {
                color: $dark;

                &:before {
                    transform: translateX(0);
                }
            }
        }
    }
}
</style>
