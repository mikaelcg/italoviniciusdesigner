<template>
    <div class="Ummense-cadastro">
        <PageHeader>
            <template v-slot:PageHeaderTitle>
                UMMENSE
            </template>
            <template v-slot:PageHeaderSubtitle>
                CADASTRO
            </template>
            <template v-slot:PageHeaderYear>
                2019
            </template>
            <template v-slot:PageHeaderDescription>
                Um processo de cadastro mais clean e mais eficaz
            </template>
            <template v-slot:PageHeaderImage>
                <img src="Cadastro/Cadastro-header.png" alt="Novo cadastro" />
            </template>
        </PageHeader>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                VISÃO GERAL
            </template>
            <template v-slot:PageItemText>
                Com o aumento de cadastrados realizados na plataforma Ummense,
                surgiu a necessidade de segmentar melhor o nosso público e
                identificar sua área de atuação. Sendo assim, o formulário de
                cadastro precisava receber novos campos e estes teriam três
                níveis no qual o usuário precisaria passar.
            </template>
        </PageItemText>

        <div class="PageImage bgGrey">
            <img src="Cadastro/Cadastro-antigo.png" alt="Cadastro antigo" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                O DESAFIO
            </template>
            <template v-slot:PageItemText>
                O modelo antigo era mais longo do que o necessário, o que gerou
                uma preocupação pelo fato de tornar o formulário extenso demais
                e propício a desistências.
            </template>
        </PageItemText>

        <div class="PageImage">
            <img src="Cadastro/Fluxo-antigo.png" alt="Fluxo antigo" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                A SOLUÇÃO
            </template>
            <template v-slot:PageItemText>
                O formulário foi dividido em dois passos: no primeiro momento
                ele tem questões essenciais para o cadastro e, no segundo, as
                informações da organização.<br /><br />
                Campos para foto do usuário e da marca da organização foram
                retirados, pois não eram cruciais no momento.<br /><br />
                Outros campos só aparecem após o preenchimento de informações
                mais importantes. Tudo para tornar o formulário mais simples e
                confortável.
            </template>
        </PageItemText>

        <div class="PageImage">
            <img src="Cadastro/Solução.png" alt="Solução" />
        </div>

        <div class="PageImage bgBlack">
            <img src="Cadastro/Form01.png" alt="Formulario 1" />
        </div>

        <div class="FormImages">
            <img src="Cadastro/Form01.png" alt="Formulario 1" />
            <img src="Cadastro/Form02.png" alt="Formulario 2" />
        </div>

        <PageItemText :background-color-black="true">
            <template v-slot:PageItemTextTitle>
                RESULTADO
            </template>
            <template v-slot:PageItemText>
                O formulário de cadastro recebeu um novo fluxo e um novo visual.
                Essas mudanças contribuíram para o aumento de cadastros na
                plataforma que hoje conta com mais de 1756 empresas registradas.
            </template>
        </PageItemText>

        <div class="PageImage bgBlack">
            <img src="Cadastro/Resultado.png" alt="Resultado" />
        </div>

        <PageItemText :background-color-black="true">
            <template v-slot:PageItemTextTitle>
                O QUE EU APRENDI?
            </template>
            <template v-slot:PageItemText>
                Esse projeto me fez lembrar que por mais que achemos que
                chegamos a melhor solução do mundo, sempre dá pra ir além. Após
                ser liberado para os usuários sentimos a necessidade de realizar
                mais alguns ajustes para potencializar ainda mais os resultados
                do formulário e agora está previsto a implantação de um
                formulário mais humanizado, fazendo o uso de um chatbot onde o
                usuário irá responder o formulário como se estivesse conversando
                com nosso bot.
            </template>
        </PageItemText>
    </div>
</template>

<script>
import PageHeader from '@/components/page-components/PageHeader'
import PageItemText from '@/components/page-components/PageItemText'

export default {
    name: 'UmmenseCadastro',
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
.Ummense-cadastro {
    .PageImage {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 10rem 0;

        img {
            max-width: 100%;
            height: auto;
        }

        &.bgBlack {
            background-color: $dark;
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

    .FormImages {
        background-color: $dark;
        display: flex;
        justify-content: center;
        align-items: center;
    }
}
</style>
