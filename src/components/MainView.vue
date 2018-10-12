<template>
    <div class="main-view">
        <h1>Hey</h1>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "MainView",
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

<style scoped>

</style>