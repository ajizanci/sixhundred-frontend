<template>
  <div class="p-1 sm:p-2 rounded bg-gray-600 shadow-xl">
    <search-field
      background="bg-gray-700"
      class="text-gray-100"
      :placeholder="placeholder"
    />
    <ul class="mt-2">
      <li v-for="(item, i) in items" :key="i" class="mb-1 text-gray-100">
        <slot :item="item"></slot>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    placeholder: {
      type: String,
      default: () => '',
    },
    items: {
      type: Array,
      default: () => [],
    },
  },
}
</script>
