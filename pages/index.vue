<template>
  <div>
    <h1>Hello Nuxt.js</h1>
    {{ message }}
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  async asyncData({ $axios }) {
    try {
      const response = await $axios.$get('/api/posts');
      return {
        message: response.message
      }
    } catch (err) {
      console.error(err);
    }
  }
}
</script>
