<template>
  <div>
    <article>
      <h1>{{ title }}</h1>
      <div>{{ details }}</div>
    </article>
  </div>
</template>

<script>
import { store } from "../store";

export default {
  name: 'Preview',
  computed: {
    title() {
      return store.state.title
    },
    details() {
      return store.state.details
    },
    email() {
      return store.state.email
    }
  }
}
</script>

<style scoped>
body { text-align: center; padding: 150px; }
h1 { font-size: 50px; }
body { font: 20px Helvetica, sans-serif; color: #333; }
article { display: block; text-align: left; width: 650px; margin: 0 auto; }
a { color: #dc8100; text-decoration: none; }
a:hover { color: #333; text-decoration: none; }
</style>
