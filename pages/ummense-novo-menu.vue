<template>
    <div class="UmmenseNovoMenu">
        <PageHeader :background-color-dark-grey="true">
            <template v-slot:PageHeaderTitle>
                UMMENSE
            </template>
            <template v-slot:PageHeaderSubtitle>
                NOVO MENU
            </template>
            <template v-slot:PageHeaderYear>
                2019
            </template>
            <template v-slot:PageHeaderDescription>
                Desenvolvimento de um menu mais consistente
            </template>
            <template v-slot:PageHeaderImage>
                <img src="Novo-menu/Novo-menu-header.png" alt="Novo menu" />
            </template>
        </PageHeader>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                VISÃO GERAL
            </template>
            <template v-slot:PageItemText>
                Com o crescimento da plataforma, a Ummense vem recebendo novas
                features, o que levou a necessidade do menu passar para a
                lateral, pois a versão horizontal não oferecia espaço
                suficiente. Já havia sido testado algumas variações até que
                chegamos a uma solução mais consistente e definitiva. O menu
                antigo:
            </template>
        </PageItemText>

        <div class="PageImage bgBlue paddingTop">
            <img src="Novo-menu/Menu-antigo.png" alt="Menu antigo" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                O DESAFIO
            </template>
            <template v-slot:PageItemText>
                No novo menu vertical, o campo de busca que antes tinha um lugar
                privilegiado no topo, passou a ser uma opção na parte inferior.
                <br /><br />
                A busca é um item importante que tem que estar visível para o
                usuário quando ele precisar e, com o mapeamento da tela
                percebemos que ela estava sendo subutilizado, muitas vezes
                passando despercebido.
            </template>
        </PageItemText>

        <div class="PageImage bgGrey paddingTop">
            <img
                src="Novo-menu/Menu-antigo-vertical.png"
                alt="Menu antigo vertical"
            />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                A SOLUÇÃO
            </template>
            <template v-slot:PageItemText>
                Para encontrar a solução, desenhamos uma jornada do usuário, e
                identificamos pontos que provavam que seria complicado procurar
                um documento sem um campo de busca acessível e nos trouxeram
                insights para encontrar a solução.
                <br /><br />
                Após algumas avaliações, decidimos inserir o campo de pesquisa
                antes dos itens do menu, tendo em vista que a busca é realizada
                dentro deles.
                <br /><br />
                Os testes A/B com os usuários comprovaram que esta versão obteve
                o melhor índice de aprovação por parte dos usuários:
            </template>
        </PageItemText>

        <div class="PageImage bgGrey paddingTop">
            <img
                src="Novo-menu/Menu-antigo-vertical-02.png"
                alt="Menu antigo vertical 02"
            />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                PORÉM...
            </template>
            <template v-slot:PageItemText>
                Após os testes identificamos outros pontos a serem melhorados.
                <br /><br />
                1 - Para verificar em qual organização o usuário está, ele
                precisava olhar na parte inferior do menu. Entretanto a
                estrutura de leitura ocidental começa pela parte superior
                esquerda, sendo assim o usuário percorria muitos caminhos até
                descobrir em qual organização ele estava logado.
                <br /><br />
                2 - O menu de configuração é uma opção de navegação importante
                na plataforma, e na versão antiga ele tinha uma posição
                desfavorecida:
            </template>
        </PageItemText>

        <div class="PageImage paddingTop">
            <img
                src="Novo-menu/Menu-antigo-vertical-02.png"
                alt="Menu antigo vertical 02"
            />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                NOVA SOLUÇÃO
            </template>
            <template v-slot:PageItemText>
                Tendo definido que o usuário precisaria fazer o login, em
                seguida identificar a organização que acessou, depois procurar
                um arquivo ou então navegar, chegamos a seguinte hierarquia de
                informação:
            </template>
        </PageItemText>

        <div class="NewSolution">
            <div class="Text">
                <span>Organização</span>
            </div>

            <div class="Divider" />

            <div class="Text">
                <span>Busca</span>
            </div>

            <div class="Divider" />

            <div class="Text">
                <span>Demais itens</span>
            </div>
        </div>

        <div class="PageImage bgLightGrey paddingTop">
            <img src="Novo-menu/Novo-menu.png" alt="Menu novo" />
        </div>

        <div class="BeforeAndAfter">
            <v-container>
                <div>
                    <h5>ANTES</h5>

                    <img src="Novo-menu/Menu-antes.png" alt="Menu antes" />
                </div>
                <div>
                    <h5>DEPOIS</h5>

                    <img src="Novo-menu/Menu-depois.png" alt="Menu depois" />
                </div>
            </v-container>
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                O RESULTADO
            </template>
            <template v-slot:PageItemText>
                Por fim, temos um menu com uma organização baseada na jornada e
                objetivos do usuário.
                <br /><br />

                Depois de apresentado e validado, foram realizados novos testes
                confirmando que a navegação se tornou mais fluida e o menu
                alcançou uma boa adesão por parte do público.
            </template>
        </PageItemText>

        <PageItemText :background-color-dark-grey="true">
            <template v-slot:PageItemTextTitle>
                O QUE EU APRENDI?
            </template>
            <template v-slot:PageItemText>
                Por fim, temos um menu com uma organização baseada na jornada e
                objetivos do usuário.
                <br /><br />

                Depois de apresentado e validado, foram realizados novos testes
                confirmando que a navegação se tornou mais fluida e o menu
                alcançou uma boa adesão por parte do público.
            </template>
        </PageItemText>

        <div class="PageImage bgDarkGrey paddingBottom">
            <img src="Novo-menu/Resultado.png" alt="Resultado" />
        </div>
    </div>
</template>

<script>
import PageHeader from '@/components/page-components/PageHeader'
import PageItemText from '@/components/page-components/PageItemText'

export default {
    name: 'UmmenseNovoMenu',
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
.UmmenseNovoMenu {
    .PageImage {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;

        img {
            max-width: 100%;
            height: auto;
        }

        &.bgGrey {
            background-color: $grey0;
        }

        &.bgLightGrey {
            background-color: #fbfbfb;
        }

        &.bgDarkGrey {
            background-color: #ebebeb;
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

        &.paddingTop {
            padding-top: 7rem;
        }

        &.paddingBottom {
            padding-bottom: 10rem;
        }

        .Image-absolute {
            position: absolute;
            top: -90%;
        }
    }

    .NewSolution {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        padding: 10rem 0;

        > .Text {
            display: flex;
            justify-content: center;
            align-items: center;
            background: #fff;
            border: 1px solid #3796f6;
            box-sizing: border-box;
            border-radius: 50px;
            width: 21rem;
            height: 6rem;

            > span {
                font-family: $opensans-semibold;
                font-style: normal;
                font-size: 1.6rem;
                line-height: 147.8%;
                text-align: center;
                color: $dark;
            }
        }

        > .Divider {
            border-left: 2px dashed #d5d5d5;
            height: 6.5rem;
        }
    }

    .BeforeAndAfter {
        background-color: $grey0;
        padding: 10rem 1.2rem 6rem 1.2rem;

        > div {
            display: flex;
            justify-content: center;
            margin: auto;

            > div {
                display: flex;
                flex-direction: column;
                justify-content: flex-start;
                align-items: flex-start;

                h5 {
                    font-family: $opensans-bold;
                    font-style: normal;
                    font-size: 1.4rem;
                    line-height: 147.8%;
                    letter-spacing: 0.1em;
                    color: $dark;
                    margin-bottom: 5rem;
                }

                &:last-child {
                    h5 {
                        position: relative;
                        left: 5.2rem;
                    }
                }
            }
        }
    }
}
</style>
