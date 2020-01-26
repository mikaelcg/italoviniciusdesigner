<template>
    <footer>
        <v-container class="Footer">
            <h3>Tem um projeto? Vamos conversar.</h3>
            <span>ola@italovinicius.com</span>

            <v-divider dark></v-divider>
        </v-container>
    </footer>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'

export default {
    name: 'Footer',
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
.Footer {
    padding: 10rem 0;

    h3 {
        font-style: normal;
        font-weight: bold;
        font-size: 3.6rem;
        line-height: 147.8%;
        color: $grey2;
    }

    span {
        font-style: normal;
        font-weight: normal;
        font-size: 2.1rem;
        line-height: 3.1rem;
        color: $grey1;
    }
}
</style>
