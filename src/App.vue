<script>
import axios from 'axios';
import { store } from './data/store';
import ProjectCard from './components/ProjectCard.vue';
import Loader from './components/partials/Loader.vue';

export default {

  name: 'App',
  components:{
    ProjectCard,
    Loader
  },
  data() {
    return {
      Titolo: 'I miei post',
      isLoaded: false,
    }
  },
  methods: {
    getApi(){
      axios.get(store.apiUrl + 'posts')
      .then(results => {
        this.isLoaded = true;
        console.log(results.data.data);
        store.posts = results.data.data;
      })
    }
  },
  mounted(){
    this.getApi();
  }
}
</script>


<template>

  <div class="container">
    <Loader v-if="!isLoaded" />
    <ProjectCard v-else />
  </div>
  
</template>



<style lang="scss">

</style>
