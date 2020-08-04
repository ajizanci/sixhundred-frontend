<template>
  <span
    class="bg-orange-400 text-gray-100 block px-2 py-1 rounded text-xs font-bold"
    >{{ hashTag }}</span
  >
</template>

<script>
export default {
  props: {
    hashTag: {
      type: String,
      default: () => 'keyword',
    },
  },
}
</script>
