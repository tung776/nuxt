<template>
  <div>
    <h2>Make API request</h2>

    <div class="container">
      <h2 v-for="post in posts" :key="post.id">{{ post.title }}</h2>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      posts: []
    };
  },
  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos")
      .then(response => {
        // console.log(response);
        this.posts = response.data;
        // console.log(this.posts);
      })
      .catch(error => {
        console.log(error);
      });
  }
};
</script>
