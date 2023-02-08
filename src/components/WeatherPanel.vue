<template>
    <div class="blur">
        <div class="input">
            <input
            v-model="query"
            @keypress.enter="getWeather"
            type="text"
            placeholder="Enter Cityname..." />
        </div>
        <div class="weatherDisplay" v-if="finishedQuery">
            <div class="weather" v-if="!responseError">
                <p id="cityName">{{ weather.name }}</p>
                <p id="cityCoords">{{ weather.coord.lat }} {{ weather.coord.lon }}</p>
                <p>{{ weather.weather[0].description }}</p>
                <p>Temp {{ weather.main.temp }} °C</p>
                <p>Windspeed {{ weather.wind.speed }} kts</p>
            </div>
            <div class="weatherError" v-else-if="responseError">
                <p>An Error occured while fetching the requested data!</p>
            </div>
        </div>    
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
.weatherDisplay {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    font-size: 19px;
    font-weight: 600;
    color: rgba(181, 215, 246, 0.597);

    background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    backdrop-filter: blur(3px);
    border-radius: 5%;
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
    width: max-content;
    margin: auto;
    margin-top: 12px;
    padding: 10px;
}
#cityName {
    font-size: 50px;
    font-weight: 600;
    margin: auto;
}
#cityCoords {
    font-size: 15px;
}
</style>

<script>
export default {
    data() {
        return {
            query: '',
            urlBase: 'https://api.openweathermap.org/data/2.5/',
            weather: {},
            finishedQuery: false,
            responseError: false
        }
    },
    methods: {
        async getWeather() {
            let response = await fetch(`${this.urlBase}weather?q=${this.query}&units=metric&APPID=${process.env.VUE_APP_API_KEY}`)
            if (response.ok) {
                this.responseError = false
                this.weather = await response.json()
                console.log(this.weather)
            } else {
                this.responseError = true
                console.log("ERROR could not fetch the data!")
            }
            this.finishedQuery = true
        }
    }
}
</script>