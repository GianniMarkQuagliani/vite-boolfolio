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
      <p class="title">{{ post.title }}</p>
      <div>
        <em>{{ post.category?.name }}</em>
        <strong v-for="tag in post.tags" :key="tag.id">{{ tag.name }}</strong>
      </div>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
h1{
  margin-bottom: 20px;  
}
ul{
  list-style-type: none;
  .title, em, strong{
    margin-right: 10px;
  }
  li{
    margin-bottom: 5px;
    display: flex;
    justify-content: space-between;
  }
}
</style>
