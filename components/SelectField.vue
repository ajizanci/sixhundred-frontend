<template>
  <label class="flex items-center" :for="name">
    <span class="block mr-1 font-semibold text-sm">{{ name }}:</span>
    <select
      class="rounded px-2 py-1 bg-white text-sm font-semibold shadow-md block focus:outline-none focus:shadow-lg"
      :name="name"
    >
      <option
        v-for="option in options"
        :key="option.value"
        :value="option.value"
      >
        {{ option.content }}</option
      >
    </select>
  </label>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: () => 'select',
    },
    options: {
      type: Array,
      default: () => [],
    },
  },
}
</script>
