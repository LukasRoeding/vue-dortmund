<template>

    <main>
      <h1>Covid-19-Cases</h1>
        <div class="weather-wrap">
          <div class="Temperature">9</div>
          <div class="Weather">Rain</div>
      </div>
    </main>

</template>

<script>
export default {
  name: 'corona',
  data() {
    return{
      api_key: '8e5ff17cdbccda50197ace99031c1c5f'
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
  background-color: rgba(255, 38, 0,0.9);
  height:100%
}
.datum{
  font-size:2vw;
  font-weight: 500;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25)
}
</style>
