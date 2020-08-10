<template>
  <div class="p-1 sm:p-2 rounded bg-gray-600 shadow-xl">
    <search-field
      background="bg-gray-700"
      class="text-gray-100"
      :placeholder="placeholder"
      @input="search"
    />
    <ul v-if="displayedItems.length" class="mt-2">
      <li
        v-for="(item, i) in displayedItems"
        :key="i"
        class="mb-1 text-gray-100"
      >
        <slot :item="item"></slot>
      </li>
    </ul>
    <span v-else class="block p-2 font-semibold text-center text-gray-100"
      >No results found.</span
    >
  </div>
</template>

<script>
import { debounce } from 'lodash'

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
    searchKey: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      displayedItems: [...this.items],
    }
  },
  methods: {
    search: debounce(function (query) {
      if (this.searchKey) {
        this.displayedItems = this.items.filter((item) =>
          item[this.searchKey].toLowerCase().includes(query)
        )
      }
    }, 100),
  },
}
</script>
