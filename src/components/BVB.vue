<template>

    <main>


          <div class="Text">Spielt der BVB heute?</div>
          <div class="Text">Nein der BVB spielt heute nicht</div>

    </main>

</template>

<script>
export default {
  name: 'bvb',
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
  color:rgb(0, 0, 0);
}
main{
  background-color: rgb(236, 253, 0);

}
.Text{
  font-size:2vw;
  font-weight: 900;
  margin: 30px 0px;
  padding: 10px 25px;
  border-radius: 16px;
}

</style>