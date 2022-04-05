<template>
  <header>
    <nav>
      <a href="#">Navbar</a>
      <router-link class="btn" to="/">Home</router-link>
      <button type="input">
        <router-link class="btn" to="/posts">Posts</router-link>
      </button>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped scss='lang'>
nav {
  min-height: 80px;
  background-color: darkgray;
}
</style>