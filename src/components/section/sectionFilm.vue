<template>
  <ul>
     <li v-for="film in sharedComponents.films" :key="film.id">
          <h3>{{film.title}}</h3>  
          <h4>{{film.original_title}}</h4> 
          <!-- <img :src="getFlegs(film.original_language)" alt=""> -->
               {{film.original_language}}
           <h5>{{film.vote_average}}</h5>
     </li>
  </ul>
</template>

<script>
import sharedComponents from '../shared/sharedComponents'
export default {
 name: 'sectionFilm',
 data(){
    return{
       sharedComponents,
       
    }
 },
 methods:{
    getFlegs(language){
       if(language === 'it' ){
          return sharedComponents.flegs.it
       }
    }
 }
}
</script>

<style>

</style>