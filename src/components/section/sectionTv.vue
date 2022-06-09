<template>
  <ul>
     <li v-for="film in sharedComponents.films" :key="film.id">
          <h3>{{film.name}} </h3> 
          <h4>{{film.original_name}} </h4> 
          <img src="" alt="">{{film.original_language}} 
          <h5> {{film.vote_average}}</h5>
     </li>
  </ul>
</template>

<script>
 import sharedComponents from '../shared/sharedComponents'
export default {
name:'setionTv',
 data(){
    return{
       sharedComponents,
    }
 }
}
</script>

<style>

</style>