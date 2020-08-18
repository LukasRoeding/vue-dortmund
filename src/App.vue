<template>
  <div id="app">
    <div class="grid-container">
      <div class="grid-left">
        <img src="../src/assets/stadt.jpg" width="100%">
        <br><br>
        Dortmund is with a population of 603,609 inhabitants as of 2020, 
        the third-largest city of Germany's most populous federal state of North Rhine-Westphalia and Germany's eighth-largest city. 
        It is the largest city (by area and population) of the Ruhr, Germany's largest urban area with some 5.1 million inhabitants, 
        as well as the largest city of Westphalia. On the Emscher and Ruhr rivers (tributaries of the Rhine), 
        it lies in the Rhine-Ruhr Metropolitan Region and is considered the administrative, commercial, and cultural centre of the eastern Ruhr. 
        Dortmund is the second largest city in the Low German dialect area after Hamburg. 
        <br><br>
      </div>
      <Weather class="grid-rigth1"/>
      <Corona class="grid-rigth2"/>
      <BVB class="grid-rigth3"/>
    </div>
    
  </div>
</template>

<script>
import Weather from './components/Weather.vue'
import Corona from './components/Corona.vue'
import BVB from './components/BVB.vue'

export default {
  name: 'App',
  components: {
    Weather,
    Corona,
    BVB
  }
}
</script>

<style>
#app{
  background-color: rgba(219, 219, 219, 0.9);
}
.grid-container{
  display: grid;
  grid-template-columns: 100%;
  grid-template-rows: auto auto auto auto;
  background-color: rgba(219, 219, 219, 0.9);
  margin-right:0px;
}
.grid-left{
  grid-column: 1;
  grid-row-end: 2;
  grid-row-start: 1;
  font-size: 3vw;
  margin:0px 10px;
  margin-top:10px
}

.grid-right1{
  grid-column: 1;
  grid-row:2;
}
.grid-right2{
  grid-column: 1;
  grid-row:3;
}
.grid-right3{
  grid-column: 1;
  grid-row:4;
}
@media screen and (min-width: 1000px){
.grid-container{
  display: grid;
  grid-template-columns: 68% 32%;
  grid-template-rows: auto auto auto;
  margin-right:10px;
}
.grid-left{
  grid-column: 1;
  grid-row-end: 4;
  grid-row-start: 1;
  height: 100vh;
  font-size: 1.7vw;
  background-color: rgba(219, 219, 219, 0.9);
  

}

.grid-right1{
  grid-column: 2;
  grid-row:1;
}
.grid-right2{
  grid-column: 2;
  grid-row:2;
}
.grid-right3{
  grid-column: 2;
  grid-row:3;
}}
</style>
