<template>
  <div class="max-w-sm rounded overflow-hidden shadow-lg my-4">
    <img class="w-full" :src="mountain.image" :alt="mountain.title" />
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2">
        {{ mountain.title }}
      </div>
      <p class="text-gray-700 text-base">
        {{ mountain.continent }} | {{ mountain.description }}
      </p>
      <nuxt-link to='/rivers'>Back</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "mountain",
  async asyncData ({ $axios, params }) {
    const slug = params.mountain
    const mountain = await $axios.$get(`https://api.nuxtjs.dev/mountains/${slug}`)
    return { mountain, slug }
  }
}
</script>

<style scoped>

</style>
