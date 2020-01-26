<template>
    <header class="Header">
        <v-container>
            <nuxt-link to="/">INÍCIO</nuxt-link>

            <nuxt-link to="/sobre">SOBRE</nuxt-link>
        </v-container>
    </header>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'

export default {
    name: 'Header',
    components: {},
    props: {},
    data: () => ({}),
    computed: {},
    watch: {},
    created() {},
    mounted() {},
    methods: {}
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
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 10;

    a {
        position: relative;
        margin-right: 100px;
        font-size: 22px;
        font-family: 'Inter-Bold';
        display: inline-block;
        overflow: hidden;
        transition: all 0.5s ease;
        color: $grey1;

        &.nuxt-link-exact-active {
            color: $grey2;

            &:before {
                transform: translateX(0);
            }
        }

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

        &:hover {
            color: $grey2;

            &:before {
                transform: translateX(0);
            }
        }
    }
}
</style>
