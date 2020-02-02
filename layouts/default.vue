<template>
    <v-app class="App">
        <template v-if="!isMobile">
            <Header></Header>
            <transition name="showMenu">
                <Header
                    v-if="hasScrolled"
                    :fixed="hasScrolled"
                    :white="whiteFixedTopMenu"
                    :activeOption="activeMenuOption"
                ></Header>
            </transition>
        </template>
        <HeaderMobile v-else></HeaderMobile>
        <v-content class="App__content">
            <nuxt />
        </v-content>
        <Footer></Footer>
    </v-app>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'

import Header from '@/components/layout/Header'
import HeaderMobile from '@/components/layout/HeaderMobile'
import Footer from '@/components/layout/Footer'

export default {
    name: 'TemplateDefault',

    components: {
        Header,
        Footer,
        HeaderMobile
    },
    props: {},
    data: () => ({
        hasScrolled: false,
        whiteFixedTopMenu: false,
        activeMenuOption: 'home',
        isMobile: null
    }),
    computed: {},
    watch: {},
    created() {},
    mounted() {
        if (this.$route.hash) {
            setTimeout(() => this.scrollTo(this.$route.hash), 1)
        }
        this.watchScroll()
        this.watchWidth()
    },
    destroyed() {
        this.destroyWatchScroll()
        this.destroyWatchWidth()
    },
    methods: {
        watchScroll() {
            window.addEventListener('scroll', this.handleScroll)
        },
        watchWidth() {
            window.addEventListener('resize', this.handleResize)
            this.handleResize()
        },

        destroyWatchScroll() {
            window.removeEventListener('scroll', this.handleScroll)
        },
        destroyWatchwWidth() {
            window.removeEventListener('resize', this.handleResize)
        },

        checkIfHasScrolled() {
            if (window.pageYOffset > 30) {
                return (this.hasScrolled = true)
            }
            return (this.hasScrolled = false)
        },

        checkTopMenuBackgroundColor() {
            if (window.pageYOffset < 800 || window.pageYOffset >= 3600) {
                return (this.whiteFixedTopMenu = true)
            }
            return (this.whiteFixedTopMenu = false)
        },

        checkActiveOption() {
            if (window.pageYOffset < 800) {
                return (this.activeMenuOption = 'home')
            }

            if (window.pageYOffset >= 800 && window.pageYOffset < 3600) {
                return (this.activeMenuOption = 'work')
            }

            if (window.pageYOffset >= 3600) {
                return (this.activeMenuOption = 'about')
            }
        },

        handleScroll(event) {
            this.checkIfHasScrolled()

            this.checkTopMenuBackgroundColor()

            this.checkActiveOption()
        },

        handleResize(event) {
            if (window.innerWidth <= 768) {
                return (this.isMobile = true)
            }
            return (this.isMobile = false)
        },

        scrollTo(hashtag) {
            setTimeout(() => {
                location.href = hashtag
            }, 1)
        }
    }
}
</script>

<style lang="scss" scoped>
// @import '@/assets/variables.scss';
.App {
    // background-color: $dark;
}

.showMenu-enter-active,
.showMenu-leave-active {
    transition: all 0.8s cubic-bezier(0.075, 0.82, 0.165, 1);
}
.showMenu-enter, .showMenu-leave-to /* .fade-leave-active below version 2.1.8 */ {
    transform: translateY(-8rem);
}
</style>
