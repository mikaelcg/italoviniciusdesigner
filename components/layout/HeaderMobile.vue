/* eslint-disable prettier/prettier */
<template>
    <header
        :class="[
            'HeaderMobile',
            { 'novo-menu': this.$route.name === 'ummense-novo-menu' },
            { 'novo-site': this.$route.name === 'ummense-novo-site' }
        ]"
    >
        <v-container>
            <v-icon @click="handleShowMenu(true)" large>mdi-menu</v-icon>
        </v-container>

        <transition name="showMenu">
            <div v-if="showMenu" class="HeaderMobile__Menu">
                <div>
                    <div class="Menu Menu__Links">
                        <h3>MENU</h3>

                        <a
                            @click="handleMenuClick('#PageHeaderId')"
                            :class="[
                                {
                                    active:
                                        activeOption === 'home' &&
                                        this.$route.name === 'index'
                                }
                            ]"
                            >Início</a
                        >
                        <a
                            @click="handleMenuClick('.About')"
                            href="javascript:void(0)"
                            >Sobre</a
                        >
                    </div>

                    <div class="Menu Menu__Projects">
                        <h3>PROJETOS</h3>

                        <a
                            @click="goTo('/agni')"
                            :class="[
                                {
                                    active: this.$route.name === 'agni'
                                }
                            ]"
                            >Agni / Aplicativo</a
                        >

                        <a
                            @click="goTo('/ummense-novo-site')"
                            :class="[
                                {
                                    active:
                                        this.$route.name === 'ummense-novo-site'
                                }
                            ]"
                            >Ummense / Novo Site</a
                        >
                        <a
                            @click="goTo('/ummense-novo-menu')"
                            :class="[
                                {
                                    active:
                                        this.$route.name === 'ummense-novo-menu'
                                }
                            ]"
                            >Ummense / Novo Menu</a
                        >
                        <a
                            @click="goTo('/ummense-cadastro')"
                            :class="[
                                {
                                    active:
                                        this.$route.name === 'ummense-cadastro'
                                }
                            ]"
                            >Ummense / Cadastro</a
                        >
                    </div>
                </div>
                <div>
                    <div class="Menu Menu__SocialMedia">
                        <v-icon>mdi-email-outline</v-icon>
                        <LinkedinIcon />
                        <BehanceIcon />
                        <v-icon>mdi-instagram</v-icon>
                    </div>

                    <div class="Menu Menu__Close">
                        <v-icon @click="handleShowMenu(false)" large
                            >mdi-close</v-icon
                        >
                    </div>
                </div>
            </div>
        </transition>
    </header>
</template>

<script>
import BehanceIcon from '@/components/icons/BehanceIcon'
import LinkedinIcon from '@/components/icons/LinkedinIcon'

export default {
    name: 'HeaderMobile',

    components: { BehanceIcon, LinkedinIcon },

    props: {
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

    data: () => ({
        showMenu: false
    }),

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
        handleShowMenu(option) {
            return (this.showMenu = option)
        },

        handleMenuClick(goTo) {
            this.showMenu = false

            if (this.$route.name === 'index') {
                this.$vuetify.goTo(goTo, this.scrollOptions)
            } else {
                this.$router.push({ name: 'index' })
                setTimeout(() => {
                    this.$vuetify.goTo(goTo, this.scrollOptions)
                }, 1000)
            }
        },

        goTo(page) {
            this.showMenu = false

            this.$router.push(page)
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';
.HeaderMobile {
    width: 100%;
    height: 6rem;
    position: relative;
    top: 0;
    left: 0;
    background-color: $dark;
    display: flex;
    justify-content: flex-start;
    align-items: center;

    > div {
        > button {
            color: $gold;
        }
    }

    &.novo-menu {
        background-color: #ebebeb;
    }

    &.novo-site {
        background-color: #f1f1f1;
    }

    &__Menu {
        width: 100vw;
        height: 100%;
        background-color: $dark;
        position: fixed;
        left: 0;
        top: 0;
        right: 0;
        bottom: 0;
        z-index: 999;
        overflow: hidden;
        overscroll-behavior: contain;
        display: flex;
        flex-direction: column;
        justify-content: space-between;

        > div:first-of-type {
            padding: 20px 0;
        }

        .Menu {
            display: flex;
            justify-content: flex-start;
            align-items: center;
            flex-direction: column;

            h3 {
                color: $gold;
                font-family: $graphik-semibold;
                font-size: 1.2rem;
                line-height: 2rem;
                letter-spacing: 0.1em;
            }

            a {
                color: $grey1;
                font-family: $graphik-regular;
                font-size: 1.8rem;
                line-height: 2rem;
                letter-spacing: 0.1em;

                &.active {
                    font-family: $graphik-semibold;
                    color: $grey2;
                }
            }

            a,
            h3 {
                margin-bottom: 2rem;
            }

            &__Links {
                margin-bottom: 3rem;
            }

            &__SocialMedia {
                flex-direction: row;
                justify-content: center;
                align-items: flex-end;
                padding: 30px 0;

                i,
                svg {
                    color: $grey1;
                    margin: 0 15px;
                }

                svg {
                    position: relative;
                    bottom: 3px;
                }
            }

            &__Close {
                border-top: 1px solid $grey3;
                padding: 10px 0;

                button {
                    color: $gold;
                }
            }
        }
    }
}

.showMenu-enter-active,
.showMenu-leave-active {
    transition: all 0.8s cubic-bezier(0.075, 0.82, 0.165, 1);
}
.showMenu-enter, .showMenu-leave-to /* .fade-leave-active below version 2.1.8 */ {
    transform: translateY(-100%);
}
</style>
