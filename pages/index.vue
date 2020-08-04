<template>
  <div class="w-full">
    <header class="w-full p-8 px-0 flex justify-center items-center flex-col">
      <div class="text-6xl p-4 pt-0">
        <img src="~/assets/logo.png" alt="sixHundred" />
      </div>
      <div class="w-11/12 sm:3/4">
        <input
          type="text"
          placeholder="Search threads"
          class="block w-full mb-4 px-4 placeholder-gray-500 py-1 border text-gray-600 border-orange-400 focus:outline-none focus:shadow rounded form-input bg-white"
        />
        <div class="flex">
          <select
            class="rounded px-2 py-1 bg-white font-semibold shadow-md block mr-2 focus:outline-none focus:shadow-lg"
          >
            <option value="" class="n">Country</option>
            <option value="" class="n">Arab</option>
            <option value="" class="n">Nigeria</option>
          </select>
          <select
            class="rounded px-2 py-1 bg-white font-semibold shadow-md block focus:outline-none focus:shadow-lg"
          >
            <option value="" class="n">Category</option>
            <option value="" class="n">Technology</option>
            <option value="" class="n">Romance</option>
          </select>
        </div>
      </div>
    </header>
    <main>
      <div class="w-full">
        <div class="w-11/12 sm:3/4 mx-auto">
          <div class="p-4 rounded bg-white overflow-hidden shadow-md">
            <span class="block mb-4 w-6 h-6 flex-shrink-0 mr-2 sm:mr-4">
              <svg
                class="text-green-500"
                fill="currentColor"
                viewBox="0 0 20 20"
              >
                <path
                  fill-rule="evenodd"
                  d="M3.293 9.707a1 1 0 010-1.414l6-6a1 1 0 011.414 0l6 6a1 1 0 01-1.414 1.414L11 5.414V17a1 1 0 11-2 0V5.414L4.707 9.707a1 1 0 01-1.414 0z"
                  clip-rule="evenodd"
                ></path>
              </svg>
            </span>
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
              <div class="p-2 pt-0">
                <span class="block text-sm font-semibold"
                  >Anefu Favour Ochoche</span
                >
                <div class="mb-1 text-xs text-gray-600">
                  <span>July 01</span> &bullet; <span>2 min read</span>
                </div>
                <div class="flex">
                  <div class="flex items-center mr-2">
                    <span class="w-4 h-4 block mr-1 items-center">
                      <svg
                        class="text-red-700"
                        fill="currentColor"
                        viewBox="0 0 20 20"
                      >
                        <path
                          fill-rule="evenodd"
                          d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"
                          clip-rule="evenodd"
                        ></path>
                      </svg>
                    </span>
                    <span class="text-xs font-semibold">200</span>
                  </div>
                  <div class="flex items-center">
                    <span class="w-4 h-4 block mr-1 items-center">
                      <svg
                        class="text-green-500"
                        fill="currentColor"
                        viewBox="0 0 20 20"
                      >
                        <path
                          fill-rule="evenodd"
                          d="M4 2a1 1 0 011 1v2.101a7.002 7.002 0 0111.601 2.566 1 1 0 11-1.885.666A5.002 5.002 0 005.999 7H9a1 1 0 010 2H4a1 1 0 01-1-1V3a1 1 0 011-1zm.008 9.057a1 1 0 011.276.61A5.002 5.002 0 0014.001 13H11a1 1 0 110-2h5a1 1 0 011 1v5a1 1 0 11-2 0v-2.101a7.002 7.002 0 01-11.601-2.566 1 1 0 01.61-1.276z"
                          clip-rule="evenodd"
                        ></path>
                      </svg>
                    </span>
                    <span class="text-xs font-semibold">100</span>
                  </div>
                </div>
                <h1 class="py-2 text-2xl font-bold">
                  How Nigeria Is Going Nowhere Fast.
                </h1>
                <p>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Enim
                  dolore commodi tenetur ad, ea nobis neque obcaecati non,
                  nesciunt molestiae earum facere a sunt. Est provident ad
                  blanditiis ducimus hic!
                </p>
                <div class="w-full flex flex-wrap mt-2 justify-end">
                  <span
                    class="bg-orange-400 text-gray-100 block px-2 py-1 rounded text-xs font-bold mr-2"
                    >politics</span
                  >
                  <span
                    class="bg-orange-400 text-gray-100 block px-2 py-1 rounded text-xs font-bold"
                    >nigeria</span
                  >
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {}
</script>
