<template>
    <div class="blur">
        <div class="input">
            <input v-model="query" type="text" placeholder="Enter Cityname or Postcode..."/>
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
    data () {
        return {
            query: '' 
        }
    }
}
</script>