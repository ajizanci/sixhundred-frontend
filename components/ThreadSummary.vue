<template>
  <div class="w-full p-4 rounded bg-white overflow-hidden shadow-md">
    <fire-icon
      v-if="thread.improvement == null"
      class="mb-4 w-6 h-6"
    ></fire-icon>
    <up-arrow
      v-else-if="thread.improvement > 0"
      class="mb-4 w-6 h-6"
    ></up-arrow>
    <span v-else-if="thread.improvement == 0">No Change</span>
    <down-arrow v-else class="mb-4 w-6 h-6"></down-arrow>
    <div class="flex items-start">
      <span class="flex-shrink-0 w-8 h-8 block">
        <svg fill="currentColor" viewBox="0 0 20 20">
          <path
            fill-rule="evenodd"
            d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-6-3a2 2 0 11-4 0 2 2 0 014 0zm-2 4a5 5 0 00-4.546 2.916A5.986 5.986 0 0010 16a5.986 5.986 0 004.546-2.084A5 5 0 0010 11z"
            clip-rule="evenodd"
          ></path>
        </svg>
      </span>
      <div class="w-full p-2 pt-0">
        <span class="block text-sm font-semibold">{{ thread.username }}</span>
        <div class="mb-1 text-xs text-gray-600">
          <span>{{ thread.pubDate }}</span> &bullet; <span>2 min read</span>
        </div>
        <div class="flex">
          <div class="flex items-center mr-2">
            <like-icon class="w-4 h-4 mr-1"></like-icon>
            <span class="text-xs font-semibold">{{ thread.likes }}</span>
          </div>
          <div class="flex items-center">
            <retweet-icon class="w-4 h-4 mr-1"></retweet-icon>
            <span class="text-xs font-semibold">{{ thread.retweets }}</span>
          </div>
        </div>
        <h1 class="py-2 text-2xl font-bold">{{ thread.title }}</h1>
        <p>{{ thread.excerpt }}</p>
        <div class="w-full flex flex-wrap mt-2 justify-end">
          <hash-tag
            v-for="hashTag in thread.hashTags"
            :key="hashTag"
            :hash-tag="hashTag"
            class="mr-2"
          ></hash-tag>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    thread: { type: Object, default: () => ({}) },
  },
  computed: {
    slug() {
      return this.title.toLowerCase().split(' ').join('-')
    },
  },
}
</script>
