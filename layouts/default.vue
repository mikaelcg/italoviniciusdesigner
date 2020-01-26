<template>
    <v-app class="App">
        <Header></Header>
        <v-content class="App__content">
            <nuxt />
        </v-content>
        <Footer></Footer>
    </v-app>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'
import Header from '@/components/layout/Header'
import Footer from '@/components/layout/Footer'

export default {
    name: 'TemplateDefault',

    components: {
        Header,
        Footer
    },
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
.App {
    background-color: $dark;
}
</style>
