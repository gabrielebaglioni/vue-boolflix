<template>
  <ul>
     <li v-for="film in sharedComponents.films" :key="film.id">
          <img :src="'http://image.tmdb.org/t/p/w342' + film.poster_path" alt="">
          <h3>{{film.title}}</h3>  
          <h4>{{film.original_title}}</h4> 
          <!-- <img :src="getFlegs(film.original_language)" alt=""> -->
            <flag :iso="getFlegs(film.original_language)"/>
               <!-- {{film.original_language}} -->
           <h5>{{film.vote_average}}</h5>
     </li>
  </ul>
</template>

<script>
import sharedComponents from '../shared/sharedComponents'
export default {
 name: 'sectionFilm',
 props:{
   films: Array,
   Tv: Array,
 },
 data(){
    return{
       sharedComponents,
       fleg:'',
    }
 },
 methods:{
    getFlegs(language){
       return language === 'en' ? 'gb' : language === 'ja' ? 'jp' : language;
    },
    
    }
 }
 

</script>

<style>

</style>