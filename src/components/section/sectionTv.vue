<template>
  <ul>
     <!-- <li v-for="Tv in sharedComponents.Tv" :key="Tv.id">
         <img :src="'http://image.tmdb.org/t/p/w342' + Tv.poster_path" alt="">
         <h3>{{Tv.name}}</h3> 
         <h4>{{Tv.original_name}}</h4>  
         <flag :iso="getFlegs(Tv.original_language)"/>
         <span v-if="Tv.vote_average <= 0">0</span>
         <span v-else>

         <i v-for="index in getStar(Tv.vote_average )" :key="index" >
         <span class=" icon-color fas fa-star" style="color:gold"></span></i>
         </span>
         <div class="trama">
            <p>
            <em><strong>trama:</strong></em>
            {{Tv.overview}}
            </p>
         </div> 
     </li> -->
  </ul>
</template>

<script>
 import sharedComponents from '../shared/sharedComponents'
export default {
name:'sectionTv',
 data(){
    return{
       sharedComponents,
       fleg: "",
    }
 },
 methods:{
      getFlegs(language) {
            return language === "en" ? "gb" : language === "ja" ? "jp" : language;
        },
 }
 
}
</script>

<style>

</style>