<template>

    <main>
        <div class="datum">{{dateBuilder()}}</div>
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
    /**fetches the current weather data form dortmund */
    fetch(`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`)
      .then(res => {
        return res.json();
      }).then(this.setResults);
  },
  methods:{
    /** applies the fetched weather data to the weather object */
  setResults (results){
    this.weather = results;
    console.log(this.weather)
  },
  /** gathers the current day, date, month and year and outputs them together as a string */
  dateBuilder(){
      let d = new Date();
      let months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
      let days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
      let day = days[d.getDay()];
      let date = d.getDate();
      let month = months[d.getMonth()];
      let year = d.getFullYear();
      return `${day} ${date} ${month} ${year}`;
  }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  text-align: center;

}
main{
  margin-top:10px;
  background-image: url("../assets/wetter.jpg");
  background-size: cover;
  color:rgb(20, 20, 20);
}
.datum{
  display:inline-block;
  font-size:2vw;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.4);
  font-weight: 900;
  border-radius: 16px;
  margin: 30px 0px;
}
.temp{
  display:inline-block;
  font-size:2vw;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.4);
  font-weight: 900;
  border-radius: 16px;
  margin: 30px 100px;
  color:rgb(0, 0, 0);
}
.weather{
  font-weight: 900;
  margin-bottom: 50px;
  display:inline-block;
  font-size:2vw;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.4);
  font-weight: 900;
  border-radius: 16px;
  margin: 30px 100px;
}
@media screen and (max-width: 1000px){
  .datum{
  display:inline-block;
  font-size:3vw;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.4);
  font-weight: 900;
  border-radius: 16px;
  margin: 30px 0px;
}
  .temp{
  display:inline-block;
  font-size:3vw;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.4);
  font-weight: 900;
  border-radius: 16px;
  margin: 30px 100px;
  color:rgb(0, 0, 0);
}
.weather{
  font-weight: 900;
  margin-bottom: 50px;
  display:inline-block;
  font-size:3vw;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.4);
  font-weight: 900;
  border-radius: 16px;
  margin: 30px 100px;
}
}
</style>
