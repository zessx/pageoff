<template>
  <div>
    <label for="title">Title</label>
    <input type="text" name="title" id="title" :value="title" @change="updateTitle">
    <label for="details">Details</label>
    <textarea name="details" id="details" :value="details" @change="updateDetails"></textarea>
    <label for="email">Contact email <span>(optionnal)</span></label>
    <input type="text" name="email" id="email" :value="email" @change="updateEmail">
  </div>
</template>

<script>
import { store } from "../store";

export default {
  name: 'Form',
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
  },
  methods: {
    updateTitle(event) {
      store.state.title = event.target.value;
    },
    updateDetails(event) {
      store.state.details = event.target.value;
    },
    updateEmail(event) {
      store.state.email = event.target.value;
    }
  }
}
</script>

<style scoped>
</style>
