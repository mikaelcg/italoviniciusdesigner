<template>
    <div class="HeaderMobile">
        <v-container>
            <v-icon large>mdi-menu</v-icon>
        </v-container>
    </div>
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
}
</style>
