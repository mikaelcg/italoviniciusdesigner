<template>
    <div class="Agni">
        <PageHeader>
            <template v-slot:PageHeaderTitle>AGNI</template>
            <template v-slot:PageHeaderSubtitle>APLICATIVO</template>
            <template v-slot:PageHeaderYear>2019</template>
            <template v-slot:PageHeaderDescription
                >Um projeto desenvolvido no NASA Space Apps.</template
            >
            <template v-slot:PageHeaderImage>
                <img src="Agni/Agni_header.png" alt="Agni App" />
            </template>
        </PageHeader>

        <PageItemText>
            <template v-slot:PageItemTextTitle>VISÃO GERAL</template>
            <template v-slot:PageItemText>
                O AGNI foi um projeto desenvolvido no NASA Space Apps, um evento
                anual que acontece em todo o mundo. Participei do desafio em
                Curitiba, concorrendo diretamente com 600 maratonistas divididos
                em 86 equipes. E com o AGNI, consegui chegar até final.
                <br />
                <br />O tema escolhido no challenge foi "Localize o Fogo" V2.0.
            </template>
        </PageItemText>

        <div class="PageImage">
            <img src="Agni/Evento.png" alt="Evento" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>O DESAFIO</template>
            <template v-slot:PageItemText>
                Nosso principal desafio era encontrar soluções que funcionassem
                tanto na cidade quanto em áreas mais afastadas, engajar o
                público e criar todo produto em apenas um final de semana.
            </template>
        </PageItemText>

        <PageItemText :backgroundColorGrey="true">
            <template v-slot:PageItemTextTitle>ESTRATÉGIAS</template>
            <template v-slot:PageItemText>
                Para entender nosso público desenhamos proto-personas baseado no
                estilo de vida das regiões que precisaríamos atingir: O público
                rural e o público urbano.
            </template>
        </PageItemText>

        <div class="PageImage alternative">
            <img
                src="Agni/Agni_informacoes_demograficas.png"
                alt="Agni Informacoes Demograficas"
            />
        </div>

        <PageItemText :backgroundColorGrey="true">
            <template v-slot:PageItemTextTitle>PESQUISAS</template>
            <template v-slot:PageItemText>
                O segundo passo foi entrevistar pessoas que tivessem um perfil
                semelhante aos das personas construídas. A partir daí, entender
                o que os usuários acham de aplicativos desse segmento.
            </template>
        </PageItemText>

        <div class="Researches__result">
            <div>
                <div>
                    <p>92 <span>%</span></p>
                    <p>Não tem um aplicativo do gênero.</p>
                </div>

                <v-divider vertical></v-divider>

                <div>
                    <p>86 <span>%</span></p>
                    <p>Dificilmente usaria.</p>
                </div>
            </div>
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>SOLUÇÃO</template>
            <template v-slot:PageItemText>
                Desenhamos uma jornada de nossas personas para levantar
                hipóteses, problemas e soluções, visando extrair ideias para o
                app. Separamos as ideias em grupos: as que seriam essenciais e
                as que seriam um plus. <br />
                <br />
                A plataforma possui versões web e mobile para monitorar, alertar
                e integrar a população no combate e prevenção de incêndios,
                utilizando dados de satélites fornecidos pela NASA e fazendo o
                cruzamento com dados dos usuário. Nela seria possível:
                <br />
                <br />
                - Detectar incêndio <br />
                <br />
                - Alertar a comunidade, grupos e órgãoscompetentes <br />
                <br />
                - Contatos de emergência <br />
                <br />
                - Status do usuário <br />
                <br />
                - Orientações em caso de risco <br />
                <br />
                - Liberação de rota para bombeiros e etc. <br />
                <br />
                - Localização de usuários <br />
                <br />
                - Integração com smart home <br />
                <br />
                - Integração com watchs <br />
                <br />
                - Gamification<br />
                <br />

                Foram levantadas diversas ideias de features PLUS e todas a
                seriam liberadas de acordo com o perfil do usuário.
            </template>
        </PageItemText>

        <PageItemText :backgroundColorGrey="true">
            <template v-slot:PageItemTextTitle>ENGAJAMENTO</template>
            <template v-slot:PageItemText>
                Buscando engajar os usuários, a proposta pretendia fazer
                campanhas de conscientização pois percebemos que apôs alguns
                minutos de conversa o público já passava a perceber valor no
                produto. E a partir daquela divisão em grupo realizada, teríamos
                duas abordagens: <br /><br />

                <b>Rural</b> - Propomos alcançar essas pessoas por meio de
                campanhas e autoridades locais. Eles seriam peças fundamentais
                na divulgação do app. <br /><br />

                Uma pesquisa realizada pelo SEBRAE mostra que
                <b
                    >cerca de 95% dos produtores rurais tem acesso ao celular.
                    Então nos casos onde não exista uma conexão com a internet,
                    eles seriam notificados por SMS ou sinal de rádio.</b
                ><br /><br />

                <b>Urbano </b> - solução para o público urbano foi
                <b>
                    transformar o Agni em uma extensão para aplicativos de GPS,
                    meteorologia e redes sociais
                </b>
                com o objetivo de atingir o maior número de pessoas sem
                necessidade de download. <br /><br />

                Somente apôs conquistar a participação do público,
                estimularíamos os downloads do app para receber as features plus
                como, por exemplo, a de integração com as Smarts Homes, Watchs e
                gameficações que trabalhariam a prevenção aos incêndios.
            </template>
        </PageItemText>

        <div class="PageImage">
            <img src="Agni/Faixa_pedestre.png" alt="Faixa pedestre" />
        </div>

        <div class="Researches__result alternative">
            <div>
                <div>
                    <p>98 <span>%</span></p>
                    <p>
                        dos usuários afirmaram que utilizariam o aplicativo após
                        serem ré-entrevistados e apresentados as soluções
                        propostas.
                    </p>
                </div>
            </div>
        </div>

        <div class="PageImage alternative bgBlue absolute">
            <img
                class="Image-absolute"
                src="Agni/Agni_alertas.png"
                alt="Agni alertas"
            />
        </div>

        <div class="PageImage alternative bgBlue">
            <img src="Agni/Agni_dashboard.png" alt="Agni dashboard" />
        </div>

        <PageItemText :backgroundColorBlue="true">
            <template v-slot:PageItemTextTitle>O QUE EU APRENDI?</template>
            <template v-slot:PageItemText>
                Nesse projeto consegui colocar em prática alguns novos
                conhecimentos que me geraram mais aprendizados porém, a
                principal lição que tirei desse hackthon foi a da importância do
                trabalho em equipe, isso é algo que carrego comigo mas nesse
                evento pelas circunstâncias, pelos sentimentos a flor da pele,
                por estar participando de uma equipe com níveis totalmente
                diferente de conhecimento, com participantes que nunca tinham se
                visto antes, o trabalho em equipe foi o que mais me marcou e nos
                levou mais longe do que eu mesmo imaginava.
            </template>
        </PageItemText>

        <div class="PageImage alternative bgBlue">
            <img src="Agni/Agni_app.png" alt="Agni app" />
        </div>
    </div>
</template>

<script>
import PageHeader from '@/components/page-components/PageHeader'
import PageItemText from '@/components/page-components/PageItemText'

export default {
    name: 'Agni',
    components: { PageHeader, PageItemText },
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

.Agni {
    .PageImage {
        position: relative;

        img {
            width: 100%;
            max-width: 100%;
            height: auto;
        }

        &.alternative {
            background-color: $grey0;
            display: flex;
            justify-content: center;
            align-items: center;

            img {
                width: auto;
                max-width: 100%;
                height: auto;
            }
        }

        &.bgBlue {
            background-color: #0a2c4f;
        }

        &.absolute {
            padding-top: 31.6%;

            @media screen and (max-width: 1600px) {
                padding-top: 55%;
            }
        }

        .Image-absolute {
            position: absolute;
            top: -90%;
        }
    }

    .Researches__result {
        background-color: $grey0;
        padding: 10rem 1.2rem;
        display: flex;
        justify-content: center;
        align-items: center;

        > div {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 83.6rem !important;
            width: 100%;

            > div {
                > p:first-child {
                    font-family: $opensans-bold;
                    font-style: normal;
                    font-size: 12rem;
                    line-height: 147.8%;
                    color: $grey3;

                    > span {
                        color: $grey1;
                    }
                }

                > p:last-child {
                    font-family: $opensans-regular;
                    font-style: normal;
                    font-size: 1.6rem;
                    line-height: 147.8%;
                    text-align: center;
                    color: $grey1;
                }
            }

            @media screen and (max-width: 768px) {
                flex-direction: column;
            }
        }

        &.alternative {
            background-color: #fff;
            padding-bottom: 31.6%;

            > div {
                justify-content: center;

                p {
                    text-align: center;
                    max-width: 56rem;
                }
            }

            @media screen and (max-width: 1600px) {
                padding-bottom: 40%;
            }
        }
    }
}
</style>
