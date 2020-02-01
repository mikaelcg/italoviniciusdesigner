<template>
    <div class="Agni">
        <PageHeader>
            <template v-slot:PageHeaderTitle>AGNI</template>
            <template v-slot:PageHeaderSubtitle>APLICATIVO</template>
            <template v-slot:PageHeaderYear>2019</template>
            <template v-slot:PageHeaderDescription>
                Um projeto desenvolvido no NASA Space Apps.
            </template>
            <template v-slot:PageHeaderImage>
                <img src="Agni/Agni_header.png" alt="Agni App" />
            </template>
        </PageHeader>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                VISÃO GERAL
            </template>
            <template v-slot:PageItemText>
                O AGNI foi um projeto desenvolvido no NASA Space Apps, um evento
                anual que acontece em todo o mundo. Participei do desafio em
                Curitiba, concorrendo diretamente com 600 maratonistas divididos
                em 86 equipes. E com o AGNI, consegui chegar até final. <br />
                <br />
                O tema escolhido no challenge foi "Localize o Fogo" V2.0.
            </template>
        </PageItemText>

        <div class="PageImage">
            <img src="Agni/Evento.png" alt="Evento" />
        </div>

        <PageItemText>
            <template v-slot:PageItemTextTitle>
                O DESAFIO
            </template>
            <template v-slot:PageItemText>
                Nosso principal desafio era encontrar soluções que funcionassem
                tanto na cidade quanto em áreas mais afastadas, engajar o
                público e criar todo produto em apenas um final de semana.
            </template>
        </PageItemText>

        <PageItemText :backgroundColorGrey="true">
            <template v-slot:PageItemTextTitle>
                ESTRATÉGIAS
            </template>
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
            <template v-slot:PageItemTextTitle>
                PESQUISAS
            </template>
            <template v-slot:PageItemText>
                O segundo passo foi entrevistar pessoas que tivessem um perfil
                semelhante aos das personas construídas. A partir daí, entender
                o que os usuários acham de aplicativos desse segmento.
            </template>
        </PageItemText>
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
    }
}
</style>
