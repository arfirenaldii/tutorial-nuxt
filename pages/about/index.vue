<template>
  <div class="container mx-auto">
    <p>About Page</p>
    <TheButton @click="handleTest">Test</TheButton>
    <client-only>
      <!-- this component will only be rendered on client-side -->
      <div>Hello client-side</div>

      <!-- loading indicator, rendered on server-side -->
      <template #placeholder>
        <div>loading server-side</div>
      </template>
    </client-only>
  </div>
</template>

<script>
export default {
  methods: {
    handleTest() {
      console.log("test");
    },
  },
  head: {
    title: "About page",
    meta: [
      {
        hid: "description",
        name: "description",
        content: "About page description",
      },
    ],
  },
};
</script>
