<template>
  <div>
    <h2>Make API request</h2>

    <div class="container row">
      <!-- <h2 v-for="post in posts" :key="post.id">{{ post.title }}</h2> -->
      <post-card v-for="post in posts" :key="post.id" :post="post" class="mr-auto ml-auto"></post-card>
    </div>
  </div>
</template>

 <script>
import axios from "axios";
import PostCard from "@/components/PostCard";

export default {
  components: {
    PostCard
  },
  data() {
    return {
      posts: []
    };
  },
  //phương thức này chạy trên cả clien và server
  async asyncData() {
    // console.log(context);
    let { data } = await axios.get(
      "https://jsonplaceholder.typicode.com/posts"
    );
    return { posts: data };
  },
  head: {
    title: "list of posts"
  }
};

// import axios from "axios";
// export default {
//   data() {
//     return {
//       posts: []
//     };
//   },
//   mounted() {
//     axios
//       .get("https://jsonplaceholder.typicode.com/todos")
//       .then(response => {
//         // console.log(response);
//         this.posts = response.data;
//         // console.log(this.posts);
//       })
//       .catch(error => {
//         console.log(error);
//       });
//   }
// };
</script>
