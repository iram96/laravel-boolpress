<template>
  <div>
    <header></header>
    <main>
      <div class="container">
        <PostsList />
      </div>
    </main>
  </div>
</template>

<script>
import PostsList from "./posts/PostsList.vue";
export default {
  name: "App",
  components: {
    PostsList,
  },
};
</script>

<style>
</style>