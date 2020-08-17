<template>

    <main>
        <div class="datum">Monday, 17th August 2020</div>
        <div class="weather-wrap" v-if="typeof weather.main != 'undefined'">
          <div class="temp">{{Math.round(weather.main.temp)}}°C</div>
          <div class="weather">{{weather.weather[0].main}}</div>
      </div>
    </main>

</template>

<script>
export default {
  name: 'weather',
  data() {
    return{
      api_key: '8e5ff17cdbccda50197ace99031c1c5f',
      url_base: "https://api.openweathermap.org/data/2.5/",
      query:'dortmund',
      weather:{}
    }
  },
  created(){
    fetch(`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`)
      .then(res => {
        return res.json();
      }).then(this.setResults);
  },
  methods:{
  setResults (results){
    this.weather = results;
    console.log(this.weather)
  }}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  text-align: center;
}
main{
  background-image: url("../assets/wetter.jpg");
  color:rgb(255, 255, 255);
}
.datum{
  font-size:2vw;
  font-weight: 500;
  margin-top:50px;
}
.temp{
  display:inline-block;
  font-size:3vw;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.25);
  font-weight: 900;
  border-radius: 16px;
  margin: 30px 0px;
  color:rgb(255, 255, 255);
}
.weather{
  font-size:2vw;
  font-weight: 500;
  margin-bottom: 50px;
}
</style>
