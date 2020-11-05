<template>
  <div>
    <nav>
      <nuxt-link to='/' class="button--green">Back</nuxt-link>
      <BaseButton @click="showAlert" />
    </nav>
    <section>
      <LazyBaseAlert v-if="show" />
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      show: false
    }
  },
  methods: {
    showAlert () {
      this.show = !this.show
    }
  }
}
</script>
<style scoped></style>
