<template>
    <footer>
        <v-container class="Footer">
            <div class="Footer__content">
                <h3>Tem um projeto? Vamos conversar.</h3>
                <span>ola@italovinicius.com</span>
            </div>

            <v-divider dark></v-divider>

            <div class="Footer__links">
                <span> © {{ currentYear }} Ítalo Vinícus </span>

                <div class="Footer__links-icons">
                    <v-tooltip
                        v-for="(icon, index) in footerIcons"
                        :key="index"
                        top
                    >
                        <template v-slot:activator="{ on }">
                            <v-icon v-on="on" medium>{{ icon.icon }}</v-icon>
                        </template>
                        <span>{{ icon.name }}</span>
                    </v-tooltip>
                </div>
            </div>
        </v-container>
    </footer>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'

export default {
    name: 'Footer',
    components: {},
    props: {},
    data: () => ({
        currentYear: new Date().getFullYear(),
        footerIcons: [
            {
                name: 'E-mail',
                icon: 'mdi-email-outline'
            },
            {
                name: 'Linkedin',
                icon: 'mdi-linkedin'
            },
            {
                name: 'Behance',
                icon: 'mdi-behance'
            },
            {
                name: 'Instagram',
                icon: 'mdi-instagram'
            }
        ]
    }),
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
    &__content {
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

    &__links {
        padding: 5rem 0;
        display: flex;
        justify-content: space-between;
        align-items: center;

        > span {
            font-style: normal;
            font-weight: 600;
            font-size: 1.6rem;
            line-height: 147.8%;

            color: #595959;
        }

        &-icons {
            display: flex;
            justify-content: center;
            align-items: flex-end;

            > i {
                color: $grey1;
                margin-left: 3rem;

                &:hover {
                    color: $gold;
                    transition: color 0.3s;
                    cursor: pointer;
                }
            }
        }
    }
}
</style>
