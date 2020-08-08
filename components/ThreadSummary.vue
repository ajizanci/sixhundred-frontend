<template>
  <div class="w-full p-2 sm:p-4 rounded overflow-hidden shadow">
    <div class="flex mb-2 sm:mb-3 md:mb-4 items-start justify-between">
      <span class="block text-lg sm:text-xl text-gray-600 font-semibold"
        >{{ position }}.</span
      >
      <fire-icon v-if="thread.improvement == null" class="w-6 h-6"></fire-icon>
      <up-arrow v-else-if="thread.improvement > 0" class="w-6 h-6"></up-arrow>
      <span v-else-if="thread.improvement == 0">No Change</span>
      <down-arrow v-else class="w-6 h-6"></down-arrow>
    </div>
    <div class="flex items-start">
      <span
        class="rounded-full border border-orange-400 overflow-hidden shadow flex-shrink-0 w-8 h-8 block"
      >
        <img
          class="object-center"
          src="~/assets/profile.jpg"
          :alt="thread.username"
        />
      </span>
      <div class="w-full p-2 pt-0">
        <span class="block text-xs md:text-sm font-semibold">{{
          thread.username
        }}</span>
        <div class="mb-1 text-xs text-gray-600">
          <span>{{ thread.pubDate }}</span>
        </div>
        <div class="flex">
          <like-icon :likes="thread.likes" class="mr-2"></like-icon>
          <retweet-icon :retweets="thread.retweets"></retweet-icon>
        </div>
        <h1
          class="py-2 text-base sm:text-lg md:text-2xl text-gray-900 font-bold"
        >
          {{ thread.title }}
        </h1>
        <p class="hidden sm:block">{{ thread.excerpt }}</p>
        <div class="w-full flex flex-wrap mt-1 md:mt-2 justify-end">
          <hash-tag
            v-for="hashTag in thread.hashTags"
            :key="hashTag"
            :hash-tag="hashTag"
            class="mr-1 mb-1 sm:mr-2 sm:mb-2"
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
    position: { type: Number, default: () => 0 },
  },
  computed: {
    slug() {
      return this.title.toLowerCase().split(' ').join('-')
    },
  },
}
</script>
