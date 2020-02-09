<template>
    <header
        :class="[
            'HeaderMobile',
            { 'novo-menu': this.$route.name === 'ummense-novo-menu' },
            { 'novo-site': this.$route.name === 'ummense-novo-site' }
        ]"
    >
        <v-container>
            <v-icon large>mdi-menu</v-icon>
        </v-container>
    </header>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'

export default {
    name: 'HeaderMobile',
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
        > i {
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
}
</style>
