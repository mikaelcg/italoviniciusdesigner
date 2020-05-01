<template>
    <footer>
        <v-container class="Footer">
            <div class="Footer__content">
                <div v-if="$route.name === 'index'" class="index">
                    <h3>Tem um projeto? Vamos conversar.</h3>
                    <span>ola@italovinicius.com</span>
                </div>

                <div v-if="$route.name === 'agni'" class="agni">
                    <nuxt-link to="/ummense-novo-menu">
                        NOVO MENU <v-icon>mdi-arrow-right</v-icon>
                    </nuxt-link>
                </div>

                <div
                    v-if="$route.name === 'ummense-novo-menu'"
                    class="ummense-novo-menu"
                >
                    <nuxt-link to="/agni">
                        <v-icon>mdi-arrow-left</v-icon>AGNI
                    </nuxt-link>
                    <nuxt-link to="/ummense-novo-site">
                        NOVO SITE <v-icon>mdi-arrow-right</v-icon>
                    </nuxt-link>
                </div>

                <div
                    v-if="$route.name === 'ummense-novo-site'"
                    class="ummense-novo-site"
                >
                    <nuxt-link to="/ummense-novo-menu">
                        <v-icon>mdi-arrow-left</v-icon>NOVO MENU
                    </nuxt-link>
                    <nuxt-link to="/ummense-cadastro">
                        CADASTRO <v-icon>mdi-arrow-right</v-icon>
                    </nuxt-link>
                </div>

                <div
                    v-if="$route.name === 'ummense-cadastro'"
                    class="ummense-cadastro"
                >
                    <nuxt-link to="/ummense-novo-site">
                        <v-icon>mdi-arrow-left</v-icon>NOVO SITE
                    </nuxt-link>
                </div>
            </div>

            <v-divider dark />

            <div class="Footer__links">
                <span>© {{ currentYear }} Ítalo Vinícus</span>

                <div class="Footer__links-icons">
                    <v-tooltip top>
                        <template v-slot:activator="{ on }">
                            <a v-on="on" href="mailto:webmaster@example.com">
                                <v-icon medium>
                                    mdi-email-outline
                                </v-icon>
                            </a>
                        </template>
                        <span>Email</span>
                    </v-tooltip>

                    <v-tooltip top>
                        <template v-slot:activator="{ on }">
                            <a
                                v-on="on"
                                href="https://www.linkedin.com/in/italovfernandes/"
                                target="__blank"
                                class="IconWrapper"
                            >
                                <LinkedinIcon />
                            </a>
                        </template>
                        <span>Linkedin</span>
                    </v-tooltip>

                    <v-tooltip top>
                        <template v-slot:activator="{ on }">
                            <a
                                v-on="on"
                                class="IconWrapper"
                                href="https://www.behance.net/italovinicius"
                                target="__blank"
                            >
                                <BehanceIcon />
                            </a>
                        </template>
                        <span>Behance</span>
                    </v-tooltip>

                    <v-tooltip top>
                        <template v-slot:activator="{ on }">
                            <a
                                v-on="on"
                                href="https://www.instagram.com/italoviniicius/"
                                target="__blank"
                            >
                                <v-icon medium>
                                    mdi-instagram
                                </v-icon>
                            </a>
                        </template>
                        <span>Instagram</span>
                    </v-tooltip>
                </div>
            </div>
        </v-container>
    </footer>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'
import BehanceIcon from '@/components/icons/BehanceIcon'
import LinkedinIcon from '@/components/icons/LinkedinIcon'

export default {
    name: 'Footer',
    components: { BehanceIcon, LinkedinIcon },
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
footer {
    background-color: $dark;

    .Footer {
        &__content {
            .index {
                padding: 10rem 0;
                h3 {
                    font-style: normal;
                    font-family: $acta-display-bold;
                    font-size: 3.6rem;
                    line-height: 147.8%;
                    color: $grey2;
                }

                span {
                    font-style: normal;
                    font-family: $graphik-regular;
                    font-size: 2.1rem;
                    line-height: 3.1rem;
                    color: $grey1;
                    margin-top: 3rem;
                }
            }

            .agni {
                display: flex;
                justify-content: flex-end;
                align-items: center;
                padding: 5rem 0;

                a {
                    font-family: $graphik-semibold;
                    font-style: normal;
                    font-size: 1.4rem;
                    line-height: 147.8%;
                    text-align: right;
                    letter-spacing: 0.1em;
                    text-transform: uppercase;
                    color: #fff;

                    > i {
                        color: $gold;
                        margin-left: 1.2rem;
                    }
                }
            }

            .ummense-novo-menu,
            .ummense-novo-site {
                display: flex;
                justify-content: space-between;
                align-items: center;
                padding: 5rem 0;

                a {
                    font-family: $graphik-semibold;
                    font-style: normal;
                    font-size: 1.4rem;
                    line-height: 147.8%;
                    text-align: right;
                    letter-spacing: 0.1em;
                    text-transform: uppercase;
                    color: #fff;

                    > i {
                        color: $gold;
                    }

                    &:first-child {
                        > i {
                            margin-right: 1.2rem;
                        }
                    }
                    &:last-child {
                        > i {
                            margin-left: 1.2rem;
                        }
                    }
                }
            }

            .ummense-cadastro {
                display: flex;
                justify-content: flex-start;
                align-items: center;
                padding: 5rem 0;

                a {
                    font-family: $graphik-semibold;
                    font-style: normal;
                    font-size: 1.4rem;
                    line-height: 147.8%;
                    text-align: right;
                    letter-spacing: 0.1em;
                    text-transform: uppercase;
                    color: #fff;

                    > i {
                        color: $gold;
                        margin-right: 1.2rem;
                    }
                }
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

                a {
                    margin-left: 3rem;

                    i {
                        color: $grey1;

                        &:hover {
                            color: $gold;
                            transition: color 0.3s;
                            cursor: pointer;
                        }
                    }
                }

                .IconWrapper {
                    display: flex;
                    margin-left: 3rem;
                    position: relative;
                    bottom: 4px;
                }
            }
        }
    }
}
</style>
