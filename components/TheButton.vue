<template>
  <button
    class="
      text-white
      bg-blue-700
      hover:bg-blue-800
      font-medium
      rounded-lg
      text-sm
      px-5
      py-2
      mr-2
      mb-2
      focus:outline-none
    "
    @click="$emit('click')"
  >
    <slot />
  </button>
</template>

<script>
export default {};
</script>
