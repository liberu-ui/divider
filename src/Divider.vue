<template>
    <div :class="['is-divider', placement]"
        :data-title="title"/>
</template>

<script>
export default {
    name: 'Divider',

    props: {
        placement: {
            type: String,
            default: 'center',
            validator: value => ['left', 'center', 'right'].includes(value),
        },
        title: {
            type: String,
            default: null,
        },
    },
};
</script>

<style lang="scss">
    .is-divider {
        height: 1px;

        &.left {
            text-align: left;

            &[data-title]::after {
                margin-left: 0.5em;
            }
        }

        &.center {
            text-align: center;
        }

        &.right {
            text-align: right;

            &[data-title]::after {
                margin-right: 0.5em;
            }
        }
    }

    .is-divider[data-title]::after {
        content: attr(data-title);
        display: inline-block;
        font-size: 1rem;
        -webkit-transform: translateY(-0.8rem);
        -ms-transform: translateY(-0.8rem);
        transform: translateY(-0.8rem);
        padding: 0 .3rem;
    }
</style>
