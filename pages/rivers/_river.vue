<template>
  <div class="max-w-sm rounded overflow-hidden shadow-lg my-4">
    <img class="w-full" :src="river.image" :alt="river.title" />
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2">
        {{ river.title }}
      </div>
      <p class="text-gray-700 text-base">
        {{ river.continent }} | {{ river.description }}
      </p>
      <nuxt-link to='/rivers'>Back</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "river",
  async asyncData ({ $axios, params }) {
    const slug = params.river
    const river = await $axios.$get(`https://api.nuxtjs.dev/rivers/${slug}`)
    return { river, slug }
  }
}
</script>

<style scoped>

</style>
