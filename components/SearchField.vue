<template>
  <div :class="background" class="rounded flex items-center px-2">
    <search-icon class="flex-shrink-0 w-5 h-5" />
    <input
      v-model="value"
      type="text"
      :placeholder="placeholder"
      class="w-full h-full bg-transparent px-2 py-1 sm:px-4 sm:py-2 text-sm focus:outline-none"
      @change="$emit('change', value)"
    />
    <close-icon
      class="flex-shrink-0 w-5 h-5 cursor-pointer"
      @click="value = ''"
    />
  </div>
</template>

<script>
export default {
  props: {
    placeholder: {
      type: String,
      default: () => 'Search...',
    },
    background: {
      type: String,
      default: () => 'bg-gray-200',
    },
  },
  data() {
    return {
      value: '',
    }
  },
}
</script>
