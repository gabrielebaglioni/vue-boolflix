<template>
  <ul>
     <li v-for="film in sharedComponents.films" :key="film.id">
          <img :src="'http://image.tmdb.org/t/p/w342' + film.poster_path" alt="">
          <h3>{{film.title}}</h3>  
          <h4>{{film.original_title}}</h4> 
          <!-- <img :src="getFlegs(film.original_language)" alt=""> -->
            <flag :iso="getFlegs(film.original_language)"/>
               <!-- {{film.original_language}} -->
           <span v-if="film.vote_average <= 0">0</span>
           <span v-else>
           <i v-for="index in getStar(film.vote_average )" :key="index" >
           <span class="star icon-color fas fa-star" style="color:gold"></span>
            </i>
           </span>
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
    getStar(vote){
      return Math.round(vote / 2);
    },
    
    }
 }
 

</script>

<style>

</style>