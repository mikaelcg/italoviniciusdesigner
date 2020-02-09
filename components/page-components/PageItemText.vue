<template>
    <div
        :class="[
            'PageItemTextContent',
            {
                backgroundColorBlack: backgroundColorBlack,
                backgroundColorGrey: backgroundColorGrey,
                backgroundColorBlue: backgroundColorBlue,
                backgroundColorDarkGrey: backgroundColorDarkGrey
            }
        ]"
    >
        <v-container class="PageItemText">
            <h3 class="PageItemText__title">
                <slot name="PageItemTextTitle"></slot>
            </h3>

            <p class="PageItemText__text">
                <slot name="PageItemText"></slot>
            </p>

            <slot name="PageItemTextContent"></slot>
        </v-container>
    </div>
</template>

<script>
export default {
    name: 'PageItemText',
    components: {},
    props: {
        backgroundColorBlack: {
            type: Boolean,
            required: false
        },
        backgroundColorGrey: {
            type: Boolean,
            required: false
        },
        backgroundColorDarkGrey: {
            type: Boolean,
            required: false
        },
        backgroundColorBlue: {
            type: Boolean,
            required: false
        }
    },
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

.PageItemText {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    padding: 10rem 1.2rem;
    max-width: 83.6rem !important;

    &__title {
        font-family: $graphik-semibold;
        font-style: normal;
        font-size: 1.6rem;
        line-height: 147.8%;
        letter-spacing: 0.1em;
        color: $dark;
        margin-bottom: 5rem;
        width: 100%;
        text-align: left;
    }

    &__text {
        font-family: $graphik-regular;
        font-style: normal;
        font-size: 2.1rem;
        line-height: 3.1rem;
        color: $grey3;
        width: 100%;
        text-align: left;
    }
}

.backgroundColorBlack {
    background-color: $dark;

    .PageItemText {
        &__title,
        &__text {
            color: #fff;
        }
    }
}

.backgroundColorGrey {
    background-color: $grey0;
}

.backgroundColorBlue {
    background-color: #0a2c4f;

    .PageItemText {
        &__title,
        &__text {
            color: #fff;
        }
    }
}

.backgroundColorDarkGrey {
    background-color: #ebebeb;
}
</style>
