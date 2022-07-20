<template>
    <div>
        <button @click="getWeather">Get Weather</button>
        <div 
        class="base" 
        v-for="weather in weatherData" 
        :key="weather.id">
           <p class="location">{{weather.city}}/{{weather.country}}</p>
           <div class="weather-icon">
             <img 
             :src="`https://camo.githubusercontent.com/bcae277e88b0b3e72e4340030547d4a5e43f32ac8717bd8378cc50d6ab1672e3/68747470733a2f2f6d656469612e77697265642e636f2e756b2f70686f746f732f3630366462613163396131356637336135393761326161312f6d61737465722f775f31363030253243635f6c696d69742f776561746865722e6a7067`">
           </div>
           <p class="temp">{{weather.temperature}}C</p>
           <p class="time">{{weather.time}}</p>
        </div>
    </div>
</template>

<script>

export default {
    data(){
        return{
            weatherData: {}
        }
    },
    methods: {
        getWeather(){
            fetch("data.json")
                .then(response => response.json()) 
                .then(data => this.weatherData = data)
                alert("Do you want to move on?")
        },
    },
}
</script>

<style scoped>
button{
    height: 80px;
    width: 160px;
    font-size: 20px;
    border-radius: 10px;
    margin-bottom: 10px;
    margin-top: 10px;
    border: 2px solid cadetblue;
    background-color: coral;
    color: black;
}
img{
    width: 100px;
    height: 90px;
}
.base{
    background-color: antiquewhite;
    border: 1px solid cadetblue;
}
.location{
    color: cadetblue;
    font-size: medium;
}
.temp{
    color: coral;
}
.time{
    color: rgb(40, 61, 119);
}
</style>