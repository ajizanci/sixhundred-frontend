<template>
  <div class="pb-10">
    <header class="p-10 text-gray-100 text-6xl text-center">
      sixHundred
    </header>
    <main
      class="bg-white text-gray-800 w-11/12 sm:w-5/6 lg:max-w-4xl rounded-md shadow-lg mx-auto"
    >
      <Nuxt />
    </main>
  </div>
</template>

<script>
export default {
  head: {
    bodyAttrs: {
      class: 'bg-gray-600',
    },
  },
}
</script>

<style scoped>
@font-face {
  font-family: 'Pacifico';
  src: url('../assets/Pacifico/Pacifico-Regular.ttf');
}

header {
  font-family: 'Pacifico', sans-serif;
}
</style>
