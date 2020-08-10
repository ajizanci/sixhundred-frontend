<template>
  <div class="p-2 sm:p-4">
    <div class="mb-2 sm:mb-4 flex justify-between items-center">
      <h1 class="text-lg md:text-2xl font-semibold">All threads by @ajz</h1>
      <button
        class="block border rounded font-semibold p-2 hover:text-gray-100 focus:outline-none hover:bg-gray-700 border-gray-700"
      >
        Download All
      </button>
    </div>
    <searchable-list v-slot="{ item }" class="p-2" :items="threads">
      <div class="flex py-1 justify-between items-center">
        <a
          href="#"
          class="font-semibold focus:outline-none hover:underline text-white block"
          >{{ item.title }}</a
        >
        <button
          class="block rounded text-sm font-semibold p-2 focus:outline-none hover:bg-gray-500 bg-gray-700"
        >
          Download
        </button>
      </div>
    </searchable-list>
  </div>
</template>

<script>
export default {
  data() {
    return {
      threads: [{ title: 'Thread 1' }, { title: 'Thread 2' }],
    }
  },
}
</script>
