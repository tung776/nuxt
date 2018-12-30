<template>
  <div class="container">
    <h4>{{ post.title}}</h4>
    <p>{{post.body}}</p>
    <nuxt-link to="/posts">Back to Posts</nuxt-link>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      post: Object
    };
  },
  async asyncData(context) {
    let { data } = await axios.get(
      `https://jsonplaceholder.typicode.com/posts/${context.params.id}`
    );
    console.log(data);
    return { post: data };
  }
};
</script>
