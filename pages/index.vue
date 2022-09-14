<template>
  <!-- <tutorial/> -->
  <div class="container mx-auto">
    <p>Hello World</p>
    <p>I am rendered on the {{ renderedOn }} side</p>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  asyncData() {
    return { renderedOn: process.client ? 'client' : 'server' }
  }
}
</script>
