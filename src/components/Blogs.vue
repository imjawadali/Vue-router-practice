<template>
  <div class="blogs">
    <h2>Blogs</h2>
    <input type="text" v-model="searchTerm" />
    <div v-for="post in filteredPosts" :key="post.id">
      <h3>{{ post.title }}</h3>
      <p>{{ post.body | snippet }}</p>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
import Axios from "axios";

export default {
  name: "Blogs",
  data() {
    return {
      posts: [],
      searchTerm: ""
    };
  },
  computed: {
    filteredPosts() {
      return this.posts.filter(post => post.title.match(this.searchTerm))
    }
  },
  created() {
    Axios.get("https://jsonplaceholder.typicode.com/posts?_limit=10")
      .then(res => (this.posts = res.data))
      .catch(err => console.log(err));
  }
};
</script>

<style scoped>
</style>
