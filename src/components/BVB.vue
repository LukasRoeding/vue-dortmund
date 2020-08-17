<template>

    <main>
      <h1>BVB</h1>
        <div class="weather-wrap">
          <div class="Temperature">9</div>
          <div class="Weather">Rain</div>
      </div>
    </main>

</template>

<script>
export default {
  name: 'bvb',
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
  background-color: rgb(255, 255, 0);
  height:100%
}
.datum{
  font-size:2vw;
  font-weight: 500;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25)
}
</style>