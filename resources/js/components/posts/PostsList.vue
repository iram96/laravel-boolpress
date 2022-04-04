<template>
  <div>
    <h2>POSTS</h2>
    <ul v-if="posts.length">
      <li v-for="post in posts" :key="post.id">
        <h3>{{ post.title }}</h3>
        <p>{{ post.post_content }}</p>
        <span :class="`badge badge-${post.category.color}`">{{
          post.category.label
        }}</span>
        <br />
        <span
          v-for="tag in post.tags"
          :key="tag.id"
          :class="`badge rounded-pill badge-${tag.class}`"
          >{{ tag.name }}</span
        >
        <br />
        <img :src="post.image" alt=" No image here! " />
      </li>
    </ul>
    <p v-else>Non ci sono post</p>
  </div>
</template>

<script>
export default {
  name: "PostsList",
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    getPosts() {
      axios
        .get("/api/posts")
        .then((res) => {
          this.posts = res.data;
        })
        .catch((err) => {
          console.log(err);
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