<template>
    <div class="warning-text">
        <h1 v-bind:class="{danger: this.danger}">{{ warningMessage }}</h1>
    </div>
</template>

<script>
export default {
    name: 'WarningText',
    props: {
        danger: Boolean
    },
    computed: {
        warningMessage: function () {
            return this.danger ?
            'A potentially hazardous asteroid is approaching earth!'
            : 'No potentially hazardouz asteroids are close to earth at the moment'
        }
    }
}
</script>

<style lang="scss" scoped>
@import '~@typopro/web-bebas-neue/TypoPRO-BebasNeue-Bold.css';
@import '~@typopro/web-bebas-neue/TypoPRO-BebasNeue-Regular.css';
.warning-text {
    padding:100px 0;
    h1 {
        font-family: 'TypoPRO Bebas Neue', 'Avenir', Helvetica, Arial, sans-serif;
        font-weight:normal;
        color: #fff;
        margin: 0;
        padding: 0;
        font-size:60px;
    }
    .danger {
        font-weight:bold;
        color: #f44336;
        font-size:70px;
    }
}
</style>
