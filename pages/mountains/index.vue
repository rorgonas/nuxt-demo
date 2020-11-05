<template>
  <div>
    <nav>
      <nuxt-link to='/' class="button--green">Back</nuxt-link>
    </nav>
    <section>
      <h1>Mountain Collection</h1>
      <ul class="grid grid-cols-3 gap-4">
        <li v-for="mountain in mountains" :key="mountain.title">
          <Card
            :image="mountain.image"
            :title="mountain.title"
            :description="mountain.description"
            :slug="mountain.slug"
            :route="'mountains'"
          ></Card>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Mountains',
  async asyncData ({ $axios, params }) {
    const mountains = await $axios.$get('https://api.nuxtjs.dev/mountains')
    return { mountains }
  },
  data () {
    return {
      mountains: []
    }
  }
}
</script>

<style scoped>

</style>
