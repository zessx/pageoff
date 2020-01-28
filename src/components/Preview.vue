<template>
  <div id="preview-body" :style="`--primary-color: ${primaryColor}; --foreground-color: ${foregroundColor}; --background-color: ${backgroundColor};`">
    <article>
      <h1>{{ title }}</h1>
      <div v-html="details"></div>
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
    primaryColor() {
      return store.state.colors.primary
    },
    foregroundColor() {
      return store.state.colors.foreground
    },
    backgroundColor() {
      return store.state.colors.background
    }
  }
}
</script>

<style lang="scss" scoped>
#preview-body {
  text-align: center;
  padding: 150px;
  font: 20px Helvetica, sans-serif;
  color: var(--foreground-color);
  background: var(--background-color);

  h1 {
    font-size: 50px;
    color: var(--primary-color);
  }

  article {
    display: block;
    text-align: left;
    width: 650px;
    margin: 0 auto;
  }

  a {
    color: var(--primary-color);
    text-decoration: none;
  }
}
</style>
