<template>
    <div class="Home">
        <PageHeader>
            <template v-slot:PageHeaderTitle>
                ÍTALO VINÍCIUS
            </template>
            <template v-slot:PageHeaderSubtitle>
                UX DESIGNER
            </template>
            <template v-slot:PageHeaderDescription>
                Olá, sou Ítalo, um designer multidisciplinar, com foco em
                produtos, serviços e experiências.
            </template>
            <template v-slot:PageHeaderImage>
                <img src="Home/Italo_Vinicius.png" alt="Ítalo Vinícius" />
            </template>
        </PageHeader>

        <PageItem
            v-for="(item, index) in pageItems"
            :key="index"
            :reverse="item.reverse"
        >
            <template v-slot:PageItemImage>
                <img :src="item.imageUrl" :alt="item.title" />
            </template>
            <template v-slot:PageItemTitle>{{ item.title }}</template>
            <template v-slot:PageItemSubtitle> {{ item.subtitle }}</template>
            <template v-slot:PageItemDescription>
                {{ item.description }}
            </template>
        </PageItem>

        <About></About>
    </div>
</template>

<script>
// import { mapActions, mapGetters, mapState } from 'vuex'
import PageHeader from '@/components/page-components/PageHeader'
import PageItem from '@/components/page-components/PageItem'
import About from '@/components/page-components/About'
export default {
    name: 'Home',
    components: { PageHeader, PageItem, About },
    props: {},
    data: () => ({
        pageItems: [
            {
                imageUrl: 'Home/agni.png',
                title: 'AGNI',
                subtitle: 'APLICATIVO',
                description: 'Projeto finalista do NASA Space Apps 2019',
                to: '/agni',
                reverse: false
            },
            {
                imageUrl: 'Home/Ummense_novo_menu.png',
                title: 'UMMENSE',
                subtitle: 'NOVO MENU',
                description:
                    'Um menu com uma organização baseada na jornada e objetivos do usuário.',
                to: '/ummense-novo-menu',
                reverse: true
            },
            {
                imageUrl: 'Home/Ummense_novo_site.png',
                title: 'UMMENSE',
                subtitle: 'NOVO SITE',
                description:
                    'Um novo site que se apresenta de maneira mais clara, moderna e consegue comunicar o que é a marca.',
                to: '/ummense-novo-site',
                reverse: false
            },
            {
                imageUrl: 'Home/Ummense_novo_formulario.png',
                title: 'UMMENSE',
                subtitle: 'NOVO FORMULÁRIO',
                description:
                    'Um formulário de cadastro com um novo fluxo e um novo visual, o que gerou mais adesão.',
                to: '/ummense-novo-formulario',
                reverse: true
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
// @import '@/assets/variables.scss';
.Home {
}
</style>
