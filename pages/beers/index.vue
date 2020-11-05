<template>
  <div>
    <nav>
      <nuxt-link to='/' class="button--green">Back</nuxt-link>
    </nav>
    <section>
      <h1>Beer Collection</h1>
      <ul class="grid grid-cols-3 gap-4">
        <li v-for="beer in beers" :key="beer.title">
          <Card
            :image="beer.image_url"
            :title="beer.name"
            :description="beer.attributes"
            :slug="beer.slug"
            :route="'beers'"
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
    const beers = await $axios.$get('https://api.nuxtjs.dev/beers')
    return { beers }
  },
  data () {
    return {
      beers: []
    }
  }
}
</script>

<style scoped>

</style>
