<template>
  <div class="w-full p-2 sm:p-4">
    <search-field />
    <div>
      <div class="flex mt-2 relative justify-between sm:mt-4">
        <select-field :options="filters[1].options" :name="filters[1].name" />
        <button
          class="text-sm font-semibold block focus:outline-none rounded px-2 py-1 bg-blue-500 text-white"
          @click="addTag = !addTag"
        >
          HashTags
        </button>
        <div
          :class="addTag ? '' : 'hidden'"
          class="absolute right-0 mt-8 p-1 rounded bg-white shadow-lg"
        >
          <search-field placeholder="Search for hashtag..." />
          <ul class="mt-2">
            <li v-for="tag in filters[0].options" :key="tag.value" class="mb-1">
              <button
                class="w-full rounded p-1 focus:outline-none hover:bg-gray-200"
                @click="addHashTag(tag)"
              >
                <span class="text-sm w-full font-semibold text-center">{{
                  tag.content
                }}</span>
                <span
                  class="text-xs px-2 py-1 rounded-full bg-gray-100 font-semibold"
                  >{{ tag.value }}</span
                >
              </button>
            </li>
          </ul>
        </div>
      </div>
      <div class="flex flex-wrap mt-4">
        <hash-tag
          v-for="tag in filterTags"
          :key="tag.value"
          :hash-tag="tag.content"
          class="mr-1 mb-1"
          @click="removeHashTag(tag)"
        />
      </div>
    </div>
    <div class="my-2 -mx-2 sm:my-4 sm:-mx-4">
      <table class="w-full">
        <tr
          v-for="(thread, i) in threads"
          :key="i"
          :class="`w-full ${i % 2 == 0 ? 'bg-gray-100' : ''}`"
        >
          <td class="pl-2 sm:pl-4 py-2">
            <span class="font-semibold">{{ i + 1 }}.</span>
          </td>
          <td class="py-2">
            <up-arrow />
          </td>
          <td class="w-1/3 py-2">
            <a
              href="#"
              class="tracking-tight text-sm md:text-base leading-tight hover:underline font-semibold"
              >{{ thread.title }}</a
            >
          </td>
          <td>
            <a
              href="#"
              class="text-xs md:text-sm text-blue-400 font-medium hover:underline"
            >
              {{ thread.username }}</a
            >
          </td>
          <td class="py-2"><like-icon :likes="thread.likes" /></td>
          <td class="pr-2 sm:pr-4 py-2">
            <retweet-icon :retweets="thread.retweets" />
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      addTag: false,
      filterTags: [],
      filters: [
        {
          name: 'Hashtags',
          options: [
            { value: 0, content: 'Politics' },
            { value: 1, content: 'Technology' },
            { value: 2, content: 'History' },
          ],
        },
        { name: 'Country', options: [{ value: 0, content: 'Nigeria' }] },
      ],
      threads: [
        {
          username: '@ajizanci',
          hashTags: ['politics', 'nigeria'],
          title:
            'How Nigeria Is Going Nowhere Fast odit laboriosam commodi natus saepe minus autem culpa reiciendis unde.',
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
        {
          username: '@ajizanci',
          hashTags: [
            'politics',
            'nigeria',
            'religion',
            'truth',
            'introspection',
          ],
          title: 'Faith vs Fate.',
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
  methods: {
    addHashTag(tag) {
      if (!this.filterTags.some((t) => t.value === tag.value))
        this.filterTags.push(tag)
    },
    removeHashTag(tag) {
      this.filterTags = this.filterTags.filter((t) => t.value !== tag.value)
    },
  },
}
</script>
