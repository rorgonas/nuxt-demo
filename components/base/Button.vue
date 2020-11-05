<template>
  <button @click="onCLick" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Lazyload Me</button>
</template>

<script>
export default {
  name: 'Button',
  methods: {
    onCLick () {
      this.$emit('click')
    }
  }
}
</script>

<style scoped>

</style>
