<template>
  <div class="w-full">
    <header class="w-full p-8 px-0 flex justify-center items-center flex-col">
      <div class="text-6xl p-4 pt-0">
        <img src="~/assets/logo.png" alt="sixHundred" />
      </div>
      <div class="w-11/12 sm:3/4">
        <search-field class="mb-4"></search-field>
        <div class="flex flex-wrap">
          <select-field
            v-for="filter in filters"
            :key="filter.name"
            :name="filter.name"
            :options="filter.options"
            class="mr-2"
          ></select-field>
        </div>
      </div>
    </header>
    <main>
      <div class="w-full">
        <div class="w-11/12 sm:3/4 mx-auto">
          <thread-summary
            v-for="thread in threads"
            :key="thread.title"
            :thread="thread"
          ></thread-summary>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      filters: [
        { name: 'Category', options: [{ value: 0, content: 'Politics' }] },
        { name: 'Country', options: [{ value: 0, content: 'Nigeria' }] },
      ],
      threads: [
        {
          username: '@ajizanci',
          hashTags: ['politics', 'nigeria'],
          title: 'How Nigeria Is Going Nowhere Fast.',
          excerpt:
            'Nobogslkgjskhglksdjlgjksljdgljsglkjgklsg jsgnslkgjlsjgs sjgnsgsng svj gsjs  sj g',
          likes: 2345,
          retweets: 120399,
          improvement: null,
          pubDate: 'Jun 03',
        },
      ],
    }
  },
}
</script>
