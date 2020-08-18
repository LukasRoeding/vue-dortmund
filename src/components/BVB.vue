<template>

    <main>


          <div class="Text">Will the BVB play today?</div>
          <div class="Text" v-if="games.includes(dateBuilder())" >
            The BVB does play today!
          </div>
          <div class="Text" v-else>
            Der BVB does not play today!
          </div>

    </main>

</template>

<script>
export default {
  name: 'bvb',
  data() {
    return{
      games: ["Friday 11 September 2020", "Saturday 19 September 2020"],
    }
  },
  created(){},
  methods:{
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
  color:rgb(0, 0, 0);
}
main{
  background-color: rgb(236, 253, 0);

}
.Text{
  font-size:2vw;
  font-weight: 900;
  margin:30px 0px;
  border-radius: 16px;
}

</style>