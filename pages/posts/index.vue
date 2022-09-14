<template>
  <div class="container mx-auto">
    <p>Posts Page</p>
    <p>I am rendered on the {{ renderedOn }} side</p>
    <ThePost />
  </div>
</template>

<script>
export default {
  async asyncData() {
    // const posts = await fetch("https://api.nuxtjs.dev/posts").then((res) =>
    //   res.json()
    // );
    // return { posts };
    return { renderedOn: process.client ? "client" : "server" };
  },
};
</script>
