<template>

    <main>
      <h1>Weather</h1>
        <div class="datum">Monday, 17th August 2020</div>
        <div class="weather-wrap">
          <div class="Temperature">9</div>
          <div class="Weather">Rain</div>
      </div>
    </main>

</template>

<script>
export default {
  name: 'weather',
  data() {
    return{
      api_key: '8e5ff17cdbccda50197ace99031c1c5f',
      url_base: "https://api.openweathermap.org/data/2.5"
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
  background-color: rgba(0, 195, 255,0.5);
  height:100%
}
.datum{
  font-size:2vw;
  font-weight: 500;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25)
}
</style>
