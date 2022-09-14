<template>
  <div>
    <p v-if="$fetchState.pending">Fetching posts...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div v-else>
      <div v-for="post in posts" :key="post.id">
        <h1 class="text-xl font-bold">{{ post.title }}</h1>
        <p>{{ post.description }}</p>
        <NuxtLink :to="`/posts/${post.id}`">
          <TheButton>Detail</TheButton>
        </NuxtLink>
      </div>
    </div>
    <TheButton class="mt-4" @click="$fetch">Refresh</TheButton>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [],
    };
  },
  async fetch() {
    this.posts = await fetch("https://api.nuxtjs.dev/posts").then((res) =>
      res.json()
    );
  },
  // fetchOnServer: false,
  // mounted() {
  //   this.fetchPosts();
  // },
  // methods: {
  //   async fetchPosts() {
  //     this.posts = await fetch("https://api.nuxtjs.dev/posts").then((res) =>
  //       res.json()
  //     );
  //   },
  // },
};
</script>
