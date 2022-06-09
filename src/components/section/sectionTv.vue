<template>
  <ul>
     <li v-for="film in sharedComponents.films" :key="film.id">
          {{film.name}} , {{film.original_name}} , {{film.original_language}} , {{film.vote_average}}
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