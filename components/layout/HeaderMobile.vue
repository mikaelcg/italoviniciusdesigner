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
                <div class="Menu Menu__Links">
                    <h3>MENU</h3>

                    <nuxt-link to="/">Inicio</nuxt-link>
                    <nuxt-link to="/">Sobre</nuxt-link>
                </div>

                <div class="Menu Menu__Projects">
                    <h3>PROJETOS</h3>

                    <nuxt-link to="/">Agni / Aplicativo</nuxt-link>
                    <nuxt-link to="/">Ummense / Novo Site</nuxt-link>
                    <nuxt-link to="/">Ummense / Novo Menu</nuxt-link>
                    <nuxt-link to="/">Ummense / Cadastro</nuxt-link>
                </div>

                <div class="Menu Menu__SocialMedia">
                    <v-icon>mdi-email-outline</v-icon>
                    <v-icon>mdi-linkedin</v-icon>
                    <v-icon>mdi-behance</v-icon>
                    <v-icon>mdi-instagram</v-icon>
                </div>

                <div class="Menu Menu__Close">
                    <v-icon @click="handleShowMenu(false)" large>
                        mdi-close
                    </v-icon>
                </div>
            </div>
        </transition>
    </header>
</template>

<script>
export default {
    name: 'HeaderMobile',

    components: {},

    props: {},

    data: () => ({
        showMenu: false
    }),

    computed: {},

    watch: {},

    created() {},

    mounted() {},

    methods: {
        handleShowMenu(option) {
            return (this.showMenu = option)
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

        .Menu {
            padding: 30px 0;
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
                font-size: 1.2rem;
                line-height: 2rem;
                letter-spacing: 0.1em;
            }

            &__Links {
            }

            &__SocialMedia {
                flex-direction: row;
                justify-content: center;

                i {
                    color: $grey1;
                }
            }

            &__Close {
                border-top: 1px solid $grey3;

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
