<template>
  <div class="container">
    <h1>Post</h1>
    <PostCard :post="post" />
  </div>
</template>

<script>
import PostCard from "../posts/PostCard.vue";
export default {
  name: "PostDetailPage",
  components: {
    PostCard,
  },
  data() {
    return {
      post: [],
    };
  },
  methods: {
    getPost() {
      axios
        .get("http://localhost:8000/api/posts/" + this.$route.params.id)
        .then((res) => {
          this.post = res.data;
        })
        .catch((err) => {
          console.error(err);
        })
        .then(() => {
          console.log("ended api call");
        });
    },
  },
  mounted() {
    this.getPost();
  },
};
</script>

<style>
</style>