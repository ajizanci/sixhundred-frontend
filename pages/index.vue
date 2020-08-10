<template>
  <div class="w-full p-2 sm:p-4">
    <search-field class="border" />
    <div>
      <div class="flex mt-2 relative justify-between sm:mt-4">
        <button
          class="text-sm border border-gray-700 hover:bg-gray-700 hover:text-gray-100 text-gray-700 mb-1 font-semibold flex items-center focus:outline-none rounded px-2 py-1"
          @click="modal = modal === 'country' ? '' : 'country'"
        >
          <span>Country:</span>
          <span class="block ml-1 font-bold">{{ country || 'Any' }}</span>
        </button>
        <searchable-list
          v-slot="{ item }"
          :items="filters[1].options"
          :class="modal === 'country' ? '' : 'hidden'"
          class="absolute left-0 mt-10"
        >
          <button
            class="w-full rounded p-1 focus:outline-none hover:bg-gray-500"
            @click="pickCountry(item)"
          >
            <span
              class="text-sm text-gray-100 w-full font-semibold text-center"
              >{{ item.content }}</span
            >
          </button>
        </searchable-list>

        <button
          class="text-sm border border-gray-700 hover:bg-gray-700 hover:text-gray-100 text-gray-700 mb-1 font-semibold flex items-center focus:outline-none rounded px-2 py-1"
          @click="modal = modal === 'tag' ? '' : 'tag'"
        >
          <span>HashTags</span>
          <chevron-up v-if="modal === 'tag'" class="ml-1" />
          <chevron-down v-else class="ml-1" />
        </button>
        <searchable-list
          v-slot="{ item }"
          :items="filters[0].options"
          :class="modal === 'tag' ? '' : 'hidden'"
          placeholder="Search hashTags..."
          class="absolute right-0 mt-10"
        >
          <button
            class="w-full rounded p-1 focus:outline-none hover:bg-gray-500"
            @click="addHashTag(item)"
          >
            <span
              class="text-sm text-gray-100 w-full font-semibold text-center"
              >{{ item.content }}</span
            >
            <span
              class="ml-1 text-xs px-2 py-1 rounded-full text-gray-700 bg-white shadow-sm font-bold"
              >{{ item.value }}</span
            >
          </button>
        </searchable-list>
      </div>
      <div class="flex flex-wrap mt-2 sm:mt-4">
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
          <td class="w-1/3 sm:w-1/2 md:w-3/5 py-2">
            <a
              href="#"
              class="block tracking-tight text-sm md:text-base leading-tight hover:underline font-semibold"
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
      modal: '',
      country: '',
      filterTags: [],
      filters: [
        {
          name: 'Hashtags',
          options: [
            { value: 0, content: 'Politics' },
            { value: 112677, content: 'Technology' },
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
    pickCountry(country) {
      this.chooseCountry = false
      this.country = country.content
    },
  },
}
</script>
