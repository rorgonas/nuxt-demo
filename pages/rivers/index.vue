<template>
  <div>
    <nav>
      <nuxt-link to='/' class="button--green">Back</nuxt-link>
      <button class="button--green" @click="$fetch">Refresh</button>
    </nav>
    <section>
      <h1>River Collection</h1>
      <div v-if="$fetchState.pending">
        Loading ....
      </div>
      <div v-else-if="$fetchState.error">
        Something went wrong
      </div>
      <div v-else>
        <ul class="grid grid-cols-3 gap-4">
          <li v-for="card in cards" :key="card.title">
            <Card
              :image="card.image"
              :title="card.title"
              :description="card.description"
              :slug="card.slug"
              :route="'rivers'"
            ></Card>
          </li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Rivers',
  async fetch () {
    this.cards = await fetch('https://api.nuxtjs.dev/rivers')
      .then((res) => {
        if (res.ok) {
          return res.json()
        }
      })
  },
  data () {
    return {
      cards: []
    }
  }
}
</script>

<style scoped>

</style>
