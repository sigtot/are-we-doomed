<template>
    <div class="main-view">
        <WarningText danger/>
    </div>
</template>

<script>
import axios from 'axios'
import WarningText from './WarningText.vue'
export default {
    name: "MainView",
    components: {
        WarningText
    },
    data () {
        return {
            asteroids: null
        }
    },
    mounted () {
        axios.get("https://api.nasa.gov/neo/rest/v1/feed?start_date=2018-09-07&api_key=API_KEY")
            .then(response => (this.asteroids = response))
    }
}
</script>

<style scoped lang="scss">
.main-view {
    background: rgba(23, 23, 23, 1);
    background: -moz-radial-gradient(center, ellipse farthest-corner, rgba(23, 23, 23, 1) 0%, rgba(48, 48, 48, 1) 100%);
    background: -webkit-gradient(radial, center center, 0px, center center, 100%, color-stop(0%, rgba(23, 23, 23, 1)), color-stop(100%, rgba(48, 48, 48, 1)));
    background: -webkit-radial-gradient(center, ellipse farthest-corner, rgba(23, 23, 23, 1) 0%, rgba(48, 48, 48, 1) 100%);
    background: -o-radial-gradient(center, ellipse farthest-corner, rgba(23, 23, 23, 1) 0%, rgba(48, 48, 48, 1) 100%);
    background: -ms-radial-gradient(center, ellipse farthest-corner, rgba(23, 23, 23, 1) 0%, rgba(48, 48, 48, 1) 100%);
    background: radial-gradient(ellipse at center, rgba(23, 23, 23, 1) 0%, rgba(48, 48, 48, 1) 100%);
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#171717', endColorstr='#303030', GradientType=1 );

    min-height:100vh;
}
</style>
