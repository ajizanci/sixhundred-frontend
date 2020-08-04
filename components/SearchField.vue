<template>
  <input
    type="text"
    placeholder="Search threads"
    class="block w-full px-4 placeholder-gray-500 py-1 border text-gray-600 border-orange-400 focus:outline-none focus:shadow rounded bg-white"
    @change="$emit('change', $event.target.value)"
  />
</template>
