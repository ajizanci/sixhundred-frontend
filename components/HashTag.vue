<template>
  <span
    class="bg-orange-400 shadow text-gray-100 flex px-2 py-1 rounded text-xs font-bold"
  >
    <span class="block mr-2">{{ hashTag }}</span>
    <close-icon
      color="text-orange-200"
      class="w-5 h-5 flex-shrink-0 cursor-pointer"
      @click="$emit('click')"
    />
  </span>
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
