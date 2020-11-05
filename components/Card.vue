<template>
  <div class="max-w-sm rounded overflow-hidden shadow-lg my-4">
    <img class="w-full" :src="image" :alt="title" />
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2">
        {{ title }}
      </div>
      <p class="text-gray-700 text-base">
        {{ description }}
      </p>
      <nuxt-link :to="`/${route}/${slug}`">
        Details
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    image: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    slug: {
      type: String,
      required: false
    },
    route: {
      type: String,
      required: false
    }
  }
}
</script>

<style scoped>

</style>
