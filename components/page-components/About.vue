<template>
    <div class="About">
        <v-container>
            <v-row>
                <v-col cols="12" md="6" class="About__vision">
                    <h3>VISÃO GERAL</h3>

                    <p>
                        UX/UI designer atuando em Curitiba/PR, trabalho no time
                        de designers da Ummense, uma plataforma de gestão de
                        projetos.
                        <br />
                        <br />
                        Procuro sempre analisar e encontrar o equilíbrio entre a
                        experiência do usuário e os objetivos de negócios, gosto
                        de encontrar soluções diferentes mas escolho as que
                        melhor solucionam os problemas propostos.
                        <br />
                        <br />
                        Muito comunicativo, gosto de estabelecer amizades e
                        acredito no trabalho em equipe.
                    </p>
                </v-col>
                <v-col cols="12" md="6" class="About__experiences">
                    <h3>EXPERIÊNCIAS</h3>

                    <div
                        v-for="(item, index) in experiences"
                        :key="index"
                        class="About__experiencies-item"
                    >
                        <h4>{{ item.title }}</h4>

                        <span
                            >{{ item.place }} / {{ item.firstDate }} -
                            {{ item.lastDate }}</span
                        >
                    </div>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'

export default {
    name: 'About',
    components: {},
    props: {},
    data: () => ({
        experiences: [
            {
                title: 'UX / UI Designer',
                place: 'Ummense',
                firstDate: 'Março 2019',
                lastDate: 'Até o momento'
            },
            {
                title: 'Diretor de Arte',
                place: 'Try Digital Performance',
                firstDate: 'Jan 2018',
                lastDate: 'Jan 2019'
            },
            {
                title: 'Designer',
                place: 'WFBD Brand Design',
                firstDate: 'Out 2015',
                lastDate: 'Jan 2018'
            },
            {
                title: 'Diretor de Arte',
                place: 'Lappann Comunicação',
                firstDate: 'Ago 2014',
                lastDate: 'Set 2015'
            },
            {
                title: 'Designer',
                place: 'LPN Comunicação',
                firstDate: 'Jan 2013',
                lastDate: 'Set 2015'
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

.About {
    background-color: $grey2;
    padding: 10rem 0;

    h3 {
        color: $gold;
        font-weight: 600;
        font-size: 1.6rem;
        line-height: 147.8%;
        letter-spacing: 0.1em;
        margin-bottom: 5rem;
    }

    h4 {
        color: $dark;
        font-weight: 600;
        margin-bottom: 0.8rem;
        font-size: 2.1rem;
        line-height: 3.1rem;
    }

    p {
        margin-bottom: 5rem;
        max-width: 55.7rem;
        font-style: normal;
        font-weight: normal;
        font-size: 2.1rem;
        line-height: 3.1rem;
        color: $grey3;
    }

    span {
        color: $dark;
        line-height: 3.1rem;
    }

    .About__experiences {
        .About__experiencies-item {
            margin-bottom: 2.5rem;
        }
    }
}
</style>
