<template>

    <main>
      <div class="cases">Covid-19-Cases:</div>
        <div class="weather-wrap" v-if="typeof corona.data != 'undefined'">
          <div class="cases">Confirmed: {{corona.data[0].confirmed}}</div>
          <div class="cases">Dead: {{corona.data[0].dead}}</div>
      </div>
    </main>

</template>

<script>
export default {
  name: 'corona',
  data() {
    return{
      corona:{}
    }
  },
  created(){
    /**fetches corona data about dortmund */
    fetch(`https://www.trackcorona.live/api/cities/dortmund`)
      .then(res => {
        return res.json();
      }).then(this.setResults);
  },
  methods:{
    /** corona object gets the fetched corona data */
  setResults (results){
    this.corona = results;
    console.log(this.corona.data)
  }}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  text-align: center;
  color:#000000;
  font-weight: 900;
}
main{
  background-image: url("../assets/corona.jpg");
  background-size: cover;
}
.cases{
  font-size:2vw;
  font-weight: 900;
  margin: 30px 100px;
  display:inline-block;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.4);
  border-radius: 16px;

}
@media screen and (max-width: 1000px){
  .cases{
  font-size:3vw;
  font-weight: 900;
  margin: 30px 100px;
  display:inline-block;
  padding: 10px 25px;
  background-color:rgba(255, 255, 255, 0.4);
  border-radius: 16px;

}
}
</style>
