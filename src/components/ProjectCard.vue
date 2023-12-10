<script>
import { store } from '../data/store';

  export default {
    name: 'ProjectCard',
    data() {
      return {
        store
      }
    },
    components:{},
    methods: {},
    mounted() {},
    computed: {}  
  }
</script>

<template>
  <h1>I miei post!</h1>
  <ul>
    <li v-for="post in store.posts" :key="post.id">
      <p>{{ post.title }}</p>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
h1{
  margin-bottom: 20px;  
}
</style>
