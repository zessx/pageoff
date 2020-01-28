<template>
  <div>
    <label for="title">Title</label>
    <input type="text" name="title" id="title" :value="title" @change="updateTitle">
    <label for="details">Details</label>
    <textarea name="details" id="details" :value="details" @change="updateDetails"></textarea>
    <label for="primary-color">Primary color</label>
    <input type="color" name="primary-color" id="primary-color" :value="primaryColor" @change="updatePrimaryColor">
    <label for="foreground-color">Foreground color</label>
    <input type="color" name="foreground-color" id="foreground-color" :value="foregroundColor" @change="updateForegroundColor">
    <label for="background-color">Background color</label>
    <input type="color" name="background-color" id="background-color" :value="backgroundColor" @change="updateBackgroundColor">
  </div>
</template>

<script>
import { store } from "../store";

export default {
  name: 'Form',
  data() {
    return {
      store
    }
  },
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
  },
  methods: {
    updateTitle(event) {
      store.state.title = event.target.value;
    },
    updateDetails(event) {
      store.state.details = event.target.value;
    },
    updatePrimaryColor(event) {
      store.state.colors.primary = event.target.value;
    },
    updateForegroundColor(event) {
      store.state.colors.foreground = event.target.value;
    },
    updateBackgroundColor(event) {
      store.state.colors.background = event.target.value;
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
