<template>
  <h1>HelloWorld</h1>
  <div class="flex">
    <PostListItems v-for="post in posts" :key="post.id" :post="post" class="card w-75 mx-auto my-3"/>
  </div>
</template>

<script>
import axios from 'axios';
import PostListItems from './PostListItems.vue';
export default {
  // data(): This is a method in the Vue component that is responsible for defining and returning the initial data for the component.
  data() {
    // return { posts: [] };: Within the data() method, an object is returned, which serves as the initial state for the component. In this case, the object contains a single property called posts, which is an empty array [].
    return {
      posts: []
    };
  },
  async created() {
    try {
      const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
      this.posts = response.data;
    } catch (error) {
      console.error(error);
    }
  },
  props: [],
  components: {PostListItems},
  name: 'PostList'
};

</script>

<style></style>

