<template>
  <main>
   <SectionFilm/>
   
  </main>
</template>

<script>
import SectionFilm from '../section/sectionFilm.vue';


export default {
    name: "BaseMain",
    components: { SectionFilm, }
}
</script>

<style lang="scss" scoped>
   main{
     background-color: #303030;
     color: white;
   }
</style>