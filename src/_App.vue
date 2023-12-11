<script>
import axios from 'axios';
import { store } from './data/store';
import ProjectCard from './components/ProjectCard.vue';
import Loader from './components/partials/Loader.vue';
import Navigator from './components/partials/Navigator.vue'; 

export default {

  name: 'App',
  components:{
    ProjectCard,
    Loader,
    Navigator
  },
  data() {
    return {
      Titolo: 'I miei post',
      isLoaded: false,
      links: [],
      paginator: {
        firstPageUrl: '',
        lastPageUrl: '',
        links: [],
        currentPage: '',
        lastPage: '',
      }
    }
  },
  methods: {
    getApi(endpoint){
      this.isLoaded = false;
      axios.get(endpoint)
      .then(results => {
        this.isLoaded = true;
        console.log(results.data.data);
        store.posts = results.data.data;
        this.paginator.links = results.data.links;
        console.log(this.paginator.links);
        this.paginator.firstPageUrl = results.data.first_page_url;
        console.log(this.paginator.firstPageUrl);
        this.paginator.lastPageUrl = results.data.last_page_url;
        console.log(this.paginator.lastPageUrl);
        this.paginator.currentPage = results.data.current_page;
        console.log(this.paginator.currentPage);
        this.paginator.lastPage = results.data.last_page;
        console.log(this.paginator.lastPage);
      })
    }
  },
  mounted(){
    this.getApi(store.apiUrl + 'posts');;
  }
}
</script>


<template>

  <div class="container">
    <Loader v-if="!isLoaded" />

    <div v-else>
      <ProjectCard  />
      <Navigator :paginator="paginator" @callApi="getApi"/>
    </div>
    
  </div>
  
</template>



<style lang="scss">

</style>
