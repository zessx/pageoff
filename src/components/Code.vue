<template>
  <div>
    <pre>
      <code>
        &lt;!doctype html&gt;
        &lt;html&gt;
          &lt;head&gt;
            &lt;title&gt;Site Maintenance&lt;/title&gt;
            &lt;style&gt;
            body { text-align: center; padding: 150px; font: 20px Helvetica, sans-serif; background: {{ backgroundColor }}; color: {{ foregroundColor }}; }
            h1 { font-size: 50px; }
            article { display: block; text-align: left; width: 650px; margin: 0 auto; }
            a { color: {{ primaryColor }}; text-decoration: none; }
            a:hover { color: {{ foregroundColor }}; text-decoration: none; }
            &lt;/style&gt;
          &lt;/head&gt;
          &lt;body&gt;
            &lt;article&gt;
              &lt;h1&gt;{{ title }}&lt;/h1&gt;
              &lt;div&gt;{{ details }}&lt;/div&gt;
            &lt;/article&gt;
          &lt;/body&gt;
        &lt;/html&gt;
      </code>
    </pre>
  </div>
</template>

<script>
import { store } from "../store";

export default {
  name: 'Code',
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
</style>
