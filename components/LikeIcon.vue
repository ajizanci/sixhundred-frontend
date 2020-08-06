<template>
  <div class="flex items-center">
    <span class="block mr-1 w-4 h-4">
      <svg class="text-red-700" fill="currentColor" viewBox="0 0 20 20">
        <path
          fill-rule="evenodd"
          d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"
          clip-rule="evenodd"
        ></path>
      </svg>
    </span>
    <span class="text-xs font-semibold">{{ likes }}</span>
  </div>
</template>

<script>
export default {
  props: {
    likes: { type: Number, default: () => 0 },
  },
}
</script>
