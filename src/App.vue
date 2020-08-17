<template>
  <div id="app">
    <div class="grid-container">
      <div class="grid-left"></div>
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
.grid-container{
  display: grid;
  grid-template-columns: 100%;
  grid-template-rows: auto auto auto auto;
}
.grid-left{
  grid-column: 1;
  grid-row-end: 2;
  grid-row-start: 1;
  background-color: rgba(224, 224, 224,0.9);
  

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
@media screen and (min-width: 800px){
.grid-container{
  display: grid;
  grid-template-columns: 67% 33%;
  grid-template-rows: auto auto auto;
}
.grid-left{
  grid-column: 1;
  grid-row-end: 4;
  grid-row-start: 1;
  height: 100vh;
  background-color: rgba(224, 224, 224,0.9);
  

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
