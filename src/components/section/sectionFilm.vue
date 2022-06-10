<template>

<div class="container">
  <h2>FILM</h2>
  <ul>
     <li v-for="film in sharedComponents.films" :key="film.id">
        <div class="container-card">
            <img :src="'http://image.tmdb.org/t/p/w342' + film.poster_path" alt="">
            <div class="overlay">
              <div class="text">
                  <h3>{{film.title}}</h3>  
                  <h4>{{film.original_title}}</h4> 
                  <!-- <img :src="getFlegs(film.original_language)" alt=""> -->
                  <flag :iso="getFlegs(film.original_language)"/>
                        <!-- {{film.original_language}} -->
                  <span v-if="film.vote_average <= 0">0</span>
                  <span v-else>
                     <!-- <i v-for="index in 5" :key="index"><span class="fa-regular fa-star"></span></i> -->
                  <i v-for="index in getStar(film.vote_average )" :key="index" >
                  <span class=" icon-color fas fa-star" style="color:gold"></span></i>
                  </span>
                  
                     <p>
                        <em><strong>trama:</strong></em>
                        {{film.overview}}
                     </p>
                
              </div>
            </div>
        </div>
         
         
     </li>
  </ul>
  <h2>serie Tv</h2>
  <SectionTv/>
   <!-- <ul>
     <li v-for="Tv in sharedComponents.Tv" :key="Tv.id">
          <img :src="'http://image.tmdb.org/t/p/w342' + Tv.poster_path" alt="">
          <h3>{{Tv.title}}</h3>  
          <h4>{{Tv.original_title}}</h4> 
         
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
     </li>
  </ul> -->
 </div>


</template>

<script>
import sharedComponents from '../shared/sharedComponents'
import SectionTv from './sectionTv.vue';
export default {
    name: "sectionFilm",
   
    data() {
        return {
            sharedComponents,
            fleg: "",
        };
    },
    methods: {
        getFlegs(language) {
            return language === "en" ? "gb" : language === "ja" ? "jp" : language;
        },
        getStar(vote) {
            return Math.round(vote / 2);
        },
    },
    components: { SectionTv }
}
 

</script>

<style lang="scss" scoped>
.container{
   width: calc(100% - 1.875rem);
   margin-left: auto ; 
   margin-right: auto;  
}
  ul{
     list-style: none;
     display: flex;
     gap: 1.25rem;
     flex-wrap: wrap;
     margin-left: 5.125rem;
 }
 img{
  width: 21.375rem;
  height: 31.25rem;
 }
 
 .container-card{
   position: relative;
   width: 100%;
   overflow-wrap: break-word; 
  
   
 }
 .overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100%;
  opacity: 0;
  transition: .5s ease;
  overflow-y: scroll;
  background-color:#BE0810;
  
 
}
.container-card:hover .overlay {
  opacity: 1;
}
.text {
  color:black;
  font-size: 20px;
  text-align: center;
  
  
}
 
</style>