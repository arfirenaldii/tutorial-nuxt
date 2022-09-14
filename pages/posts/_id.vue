<template>
  <div class="container mx-auto">
    <TheButton @click="$router.back()">Back</TheButton>
    <h1 class="text-xl font-bold">{{ post.title }}</h1>
    <img class="h-60 block my-0 mx-auto" :src="post.image" :alt="post.title" />
    <p class="mt-4">{{ post.description }}</p>
  </div>
</template>

<script>
export default {
  async asyncData({ params }) {
    const id = params.id;
    const post = await fetch(`https://api.nuxtjs.dev/posts/${id}`).then((res) =>
      res.json()
    );
    return { post };
  },
};
</script>
