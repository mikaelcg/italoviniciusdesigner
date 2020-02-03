<template>
    <div class="UmmenseNovoSite">
        <PageHeader :backgroundColorGrey="true" :novoSite="true"
            ><template v-slot:PageHeaderTitle>UMMENSE</template>
            <template v-slot:PageHeaderSubtitle>APLICATIVO</template>
            <template v-slot:PageHeaderYear>2019</template>
            <template v-slot:PageHeaderDescription>
                Desenvolvimento de um menu mais consistente
            </template>
            <template v-slot:PageHeaderImage>
                <img
                    src="Novo-site/Ummense-novo-site-header.png"
                    alt="Novo site"
                />
            </template>
        </PageHeader>

        <PageItemText>
            <template v-slot:PageItemTextTitle>VISÃO GERAL</template>
            <template v-slot:PageItemText>
                A Ummense é uma plataforma de gestão de negócios que vem
                conquistando espaço no mercado. Seu objetivo é ser uma
                ferramenta completa, oferecendo diversos recursos relevantes.
                Com ela você consegue criar fluxos completos de uma empresa,
                como comercial, administrativo ou financeiro por exemplo, e
                desenvolver um projeto que se integre suas etapas em todos eles
                simultaneamente.<br /><br />
                Ainda é possível criar diversas automações, formulários
                externos, entre outras funções de compartilhamento fácil com o
                cliente.
            </template>
        </PageItemText>

        <div class="PageImage">
            <img src="Novo-site/Ummense-pages.png" alt="Paginas" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>O DESAFIO</template>
            <template v-slot:PageItemText>
                Através de uma pesquisa, constatamos que o antigo site não era
                atrativo. Havia muito conteúdo desnecessário, pouca hierarquia
                visual e baixa ilustração das informações e tudo isso em apenas
                uma página.
            </template>
        </PageItemText>

        <div class="PageImage bgLightPurple">
            <img src="Novo-site/Ummense-pages-2.png" alt="Paginas 2" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>A SOLUÇÃO</template>
            <template v-slot:PageItemText>
                Desenvolvemos textos mais objetivos, exploramos imagens e
                distribuímos o conteúdo em páginas, ao invés de uma landing
                page. Isso contribuiu para uma melhor performance na pesquisa do
                Google. <br /><br />Este foi o novo fluxo escolhido:
            </template>
        </PageItemText>

        <div class="PageImage">
            <img src="Novo-site/Flows.png" alt="Fluxo" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>WIREFRAMES</template>
            <template v-slot:PageItemText>
                O passo seguinte foi fazer uso do grid para distribuir o
                conteúdo, ter bons espaços em branco, um layout clean e mais
                dinâmico.
            </template>
        </PageItemText>

        <div class="PageImage">
            <img src="Novo-site/Wireframes.png" alt="Wireframes" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>O RESULTADO</template>
            <template v-slot:PageItemText>
                O novo site se apresenta de maneira mais clara, moderna e
                consegue comunicar o que é a marca. O número de acessos em
                relação a versão anterior aumentou e a taxa de rejeição baixou
                bastante.
            </template>
        </PageItemText>
    </div>
</template>

<script>
import PageHeader from '@/components/page-components/PageHeader'
import PageItemText from '@/components/page-components/PageItemText'

export default {
    name: 'UmmenseNovoSite',
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
.UmmenseNovoSite {
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

        &.bgLightPurple {
            background-color: #f8f8fa;
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
}
</style>
