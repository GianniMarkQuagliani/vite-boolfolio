<script>
import axios from 'axios';
import { store } from './data/store';
import ProjectCard from './components/ProjectCard.vue';

export default {

  name: 'App',
  components:{
    ProjectCard
  },
  data() {
    return {
      Titolo: 'I miei post',
    }
  },
  methods: {
    getApi(){
      axios.get(store.apiUrl + 'posts')
      .then(results => {
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
    <ProjectCard />
  </div>
  
</template>



<style lang="scss">

</style>
