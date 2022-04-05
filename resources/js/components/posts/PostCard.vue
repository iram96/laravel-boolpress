<template>
  <div class="container ciao">
    <div class="card d-flex flex-col m-0" style="width: 18rem">
      <img :src="post.image" class="card-img-top" alt="..." />
      <div class="card-body">
        <h5 class="card-title">{{ post.title }}</h5>
        <p class="card-text">
          {{ post.post_content }}
        </p>
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
        <router-link
          :to="{ name: 'show', params: { id: post.id } }"
          class="btn btn-primary"
          >Show</router-link
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PostCard",
  props: ["post"],
};
</script>

<style>
</style>