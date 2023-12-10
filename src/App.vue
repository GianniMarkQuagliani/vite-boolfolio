<script>
import axios from 'axios';
import { store } from './data/store';

export default {

  name: 'App',
  data() {
    return {
      Titolo: 'boolfolio',
    }
  },
  methods: {
    getApi(){
      axios.get(store.apiUrl + 'posts')
      .then(results => {
        console.log(results.data);
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
    <h1>{{Titolo}}</h1>
  </div>
  
</template>



<style lang="scss">

</style>
