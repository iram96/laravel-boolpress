<template>
  <section class="container">
    <span class="font-weight-bolder text-monospace">404 | Page Not Found</span>
    <button @click="$router.back()" class="">Back</button>
  </section>
</template>

<script>
export default {
  name: "NotFoundPage",
};
</script>

<style>
</style>