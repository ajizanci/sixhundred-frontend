<template>
  <div class="w-full">
    <header
      class="w-full flex p-3 mb-8 flex-wrap md:flex-no-wrap h-auto md:h-16 bg-orange-100 justify-between opacity-75"
    >
      <div class="h-full flex-shrink-0">
        <img
          class="h-full object-center"
          src="~/assets/logo.png"
          alt="sixHundred"
        />
      </div>
      <div
        class="w-full h-full justify-center flex flex-wrap md:flex-no-wrap items-center"
      >
        <search-field class="w-full mb-3 md:mb-0 mx-3"></search-field>
        <div class="flex items-center">
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
        <div class="w-full sm:w-5/6 md:w-3/4 mx-auto">
          <thread-summary
            v-for="(thread, index) in threads"
            :key="thread.title"
            :thread="thread"
            :position="index + 1"
            class="sm:mb-4"
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
          authorImg: '/assets/profile.jpg',
        },
        {
          username: '@ajizanci',
          hashTags: [
            'politics',
            'nigeria',
            'religion',
            'truth',
            'introspection',
          ],
          title: 'A License To Lie?.',
          excerpt:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. A impedit quod eveniet, et, eaque magni maiores itaque ex, aliquid cupiditate tenetur nostrum fugit expedita reiciendis ullam nam odit nisi blanditiis?',
          likes: 2345,
          retweets: 120399,
          improvement: 1,
          pubDate: 'Jun 03',
          authorImg: '/assets/profile.jpg',
        },
      ],
    }
  },
}
</script>
