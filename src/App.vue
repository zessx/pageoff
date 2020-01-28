<template>
  <div id="app">
    <h1>Page<span>/</span>Off</h1>
    <p class="subtitle">Quickly generate maintenance pages</p>

    <section class="tabs">
      <input id="tab-settings" type="radio" name="tab-group" data-tab="settings" checked="checked" />
      <label for="tab-settings">Settings</label>
      <input id="tab-preview" type="radio" name="tab-group" data-tab="preview" />
      <label for="tab-preview">Preview</label>
      <input id="tab-code" type="radio" name="tab-group" data-tab="code" />
      <label for="tab-code">Code</label>

      <div data-content="settings">
        <Form/>
      </div>
      <div data-content="preview">
        <Preview/>
      </div>
      <div data-content="code">
        <Code/>
      </div>
    </section>
  </div>
</template>

<script>
import Form from './components/Form.vue'
import Code from './components/Code.vue'
import Preview from './components/Preview.vue'

export default {
  name: 'app',
  components: {
    Form,
    Code,
    Preview
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  text-transform: uppercase;

  span {
    color: red;
  }
}

.subtitle {

}

.tabs {

}

[data-tab] {
}

[data-content] {
  border: 1px solid;
  display: none;
}

[data-tab="settings"]:checked ~ [data-content="settings"] {
  display: block;
}

[data-tab="preview"]:checked ~ [data-content="preview"] {
  display: block;
}

[data-tab="code"]:checked ~ [data-content="code"] {
  display: block;
}

</style>
