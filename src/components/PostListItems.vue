<template>
  <div>
    <h3>{{ post.title }}</h3>
    <p>{{ post.body }}</p>
    
  </div>
</template>

<script>

export default {
  data() {
    return {
      posts: []
    };
  },
 
  props: ["post"],
  components: {},
  name: 'PostListItems'
};

</script>

<style></style>

