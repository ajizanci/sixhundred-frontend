<template>
  <div class="w-full">
    <header
      class="w-full flex p-3 mb-8 flex-wrap md:flex-no-wrap h-auto md:h-16 bg-orange-100 justify-between opacity-75"
    >
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
        <div class="p-3">
          <div class="mb-2">
            <div class="flex items-center mb-1">
              <img
                src="~/assets/profile.jpg"
                alt="User"
                class="block mr-1 flex-shrink-0 w-8 h-8 rounded-full border"
              />
              <span class="block font-semibold">@ajizanci</span>
            </div>
            <div class="flex">
              <like-icon :likes="threads[0].likes" class="mr-2"></like-icon>
              <retweet-icon :retweets="threads[0].likes"></retweet-icon>
            </div>
          </div>
          <div class="mb-4">
            <div class="flex flex-wrap items-center justify-between">
              <h1
                class="mb-2 leading-tight text-2xl font-semibold text-gray-900"
              >
                I Wanna Live Life Like it is my last day on earth
              </h1>
              <button
                class="block flex-shrink-0 text-xs sm:text-sm rounded border p-2 border-green-500 text-green-500 font-semibold"
              >
                Download Markdown
              </button>
            </div>
          </div>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius possimus
          minus maxime, facilis quo exercitationem voluptas non voluptates
          <pre
            class="w-full overflow-scroll text-white my-1 rounded bg-gray-900"
          >
          molestiae porro quod distinctio! Possimus blanditiis distinctio hic,
          velit rerum culpa atque? Lorem, ipsum dolor sit amet consectetur
          adipisicing elit. Accusantium assumenda quis porro ad doloremque. Ut
          voluptatibus, tenetur sed sunt, odit nam consectetur porro tempora
          accusantium cumque nihil blanditiis praesentium culpa! Debitis enim
          </pre>
          deleniti earum non? A culpa ad nesciunt quasi sequi nam. Blanditiis
          minima praesentium necessitatibus porro, eius debitis aspernatur nam
          impedit temporibus atque! Eius ullam ut repellendus reiciendis ex!
          Officiis quibusdam odit repudiandae sapiente! Deleniti enim dolorum,
          quod sit saepe qui cupiditate et architecto sint rerum quisquam
          <blockquote
            class="border-l-4 bg-white p-3 border-orange-400 text-gray-900 my-1 opacity-75 font-bold"
          >
            veritatis exercitationem harum soluta culpa facilis nihil, fuga
            ullam commodi, esse quae! Lorem ipsum dolor sit amet consectetur
            adipisicing elit. Labore ad quisquam sunt velit tenetur. Ducimus,
            laboriosam! Quod ut dolorem dolor quas quidem, nesciunt quam, porro
            non id, sequi aperiam sapiente. Architecto, asperiores fugit error
            repellendus
          </blockquote>
          debitis, iusto cum rem quo perferendis vel itaque, molestias sint iste
          quos harum. Minus, ea repellat. Aliquam ipsam rerum ex optio corrupti
          aut quia. Beatae. Numquam assumenda fugit corrupti asperiores dolore
          cum odit totam, sed soluta illum exercitationem quaerat vel. Aliquam,
          tempora doloremque provident ab, pariatur nobis explicabo repellendus,
          voluptatem et eligendi incidunt velit inventore?
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
