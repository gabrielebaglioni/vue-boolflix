<template>
  <ul>
     <li v-for="film in sharedComponents.films" :key="film.id">
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
 data(){
    return{
       sharedComponents,
       fleg:'',
    }
 },
 methods:{
    getFlegs(language){
       return language === 'en' ? 'gb' : language === 'ja' ? 'jp' : language;
    }
 },
 created(){
     this.getFlegs(sharedComponents.films)
 }
}
</script>

<style>

</style>