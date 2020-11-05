<template>
  <article>
    <div class="sm:w-1/4 p-2">
      <div class="bg-white px-6 py-8 rounded-lg shadow-lg text-center">
        <div class="mb-3">
          <img
            class="w-auto mx-auto rounded-full"
            :src="beer.img_url"
            alt=""
          />
        </div>
        <h2 class="text-xl font-medium text-gray-700">{{ beer.title }}</h2>
        <span class="text-blue-500 block mb-5">{{ beer.description }}</span>

        <nuxt-link to='/beers'>Beer Collection</nuxt-link>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  name: "beer",
  async asyncData ({ $content, params }) {
    const slug = params.beer
    const beer = await $content('beers', slug).fetch()
    return { beer, slug }
  }
}
</script>

<style scoped>

</style>
