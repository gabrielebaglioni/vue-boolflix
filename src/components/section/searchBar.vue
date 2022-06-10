<template>
  <form @submit.prevent="getFilmAndTv">
      <input class="input-bar" type="text" placeholder="Cerca" v-model="search" />
     
  </form>
</template>

<script>
import axios from 'axios'
import sharedComponents from '../shared/sharedComponents';
export default {
  name:'searchBar',
  data(){
     return{
        search:'',
        sharedComponents,
        
     }
  },
  methods:{
     getFilmAndTv(){
        axios.get('https://api.themoviedb.org/3/search/movie',{
           params:{
             api_key:'16322f9823087a057b8e50373be143e8',
              query: this.search,
              language: 'it-IT'

           }
         }
        ).then((response) =>{
           sharedComponents.films = response.data.results;

        }).catch((error) =>{
           console.log(error);

        });
        axios.get('https://api.themoviedb.org/3/search/tv',{
           params:{
             api_key:'16322f9823087a057b8e50373be143e8',
              query: this.search,
              language: 'it-IT'

           }
         }
        ).then((response) =>{
           sharedComponents.Tv = response.data.results;

        }).catch((error) =>{
           console.log(error);

        })
     }
  },
}
</script>

<style lang="scss" scoped>
 input{
   width: 20.25rem;
   height: 25px;
   border-radius: 5px;
   border: 2px solid #BE0810;
   
    outline-offset: 0px;
    outline: none;
 }

</style>