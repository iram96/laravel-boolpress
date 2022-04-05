<template>
  <div>
    <h2>POSTS</h2>
    <div class="container">
      <!-- <div v-if="posts.length" class="d-flex flex-row bd-highlight">
        <div v-for="post in posts" :key="post.id" class="p-2 bd-highlight">
          <h3>{{ post.title }}</h3>
          <p>{{ post.post_content }}</p>
          <span :class="`badge badge-${post.category.color}`">{{
            post.category.label
          }}</span>
          <br />
          <span
            v-for="tag in post.tags"
            :key="tag.id"
            :class="`badge bg-${tag.class}`"
            >{{ tag.name }}</span
          >
          <br />
          <img :src="post.image" alt=" No image here! " />
        </div>
      </div> -->
      <div v-if="posts.length" class="d-flex flex-row">
        <PostCard v-for="post in posts" :key="post.id" :post="post" />
      </div>
      <p v-else>Non ci sono post</p>
    </div>
  </div>
</template>

<script>
import PostCard from "./PostCard.vue";

export default {
  name: "PostsList",
  components: { PostCard },
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    getPosts() {
      axios
        .get("http://localhost:8000/api/posts")
        .then((res) => {
          this.posts = res.data;
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
    this.getPosts();
  },
};
</script>

<style>
</style>