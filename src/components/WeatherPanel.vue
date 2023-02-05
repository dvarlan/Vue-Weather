<template>
    <div class="blur">
        <div class="input">
            <input
            v-model="query"
            @keypress.enter="getWeather"
            type="text"
            placeholder="Enter Cityname or Postcode..." />
        </div>
        <p>{{ query }}</p>
    </div>
</template>

<style>
input {
    margin: auto;
    margin-top: 12px;
    padding: 20px 20px;
    height: 5px;
    width: 200px;
    border-radius: 5%;
}
</style>

<script>
export default {
    data() {
        return {
            query: '',
            urlBase: 'https://api.openweathermap.org/data/2.5/',
            weather: {}
        }
    },
    methods: {
        async getWeather() {
            // Returns 401 Error -> Key probably not activated yet
            let response = await fetch(`${this.urlBase}weather?q=${this.query}&units=metric&APPID=${process.env.VUE_APP_API_KEY}`)
            if (response.ok) {
                this.weather = await response.json()
                console.log(this.weather)
            } else {
                console.log("ERROR could not fetch the data!")
            }
        }
    }
}
</script>