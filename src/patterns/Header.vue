<template>
  <component :is="type" class="c-header">
    <logo />
    <nav-bar active="Demo" :navItems="[
      {name: 'About', component: 'Demo', href: '/#/'},
      {name: 'Blog', href: 'http://localhost:6060/'},
      {name: 'Contact', href: 'http://bradfrost.com'},
      {name: 'Login', href: 'http://ianfrostweather.com'}
    ]"/>
  </component>
</template>

<script>
/**
 * Used as main page navigation in templates.
 */
export default {
  name: "c-header",
  status: "ready",
  release: "1.0.0",
  model: {
    prop: "active",
  },
  props: {
    /**
     * The html element name used for the component.
     */
    type: {
      type: String,
      default: "header",
    },
  },
}
</script>

<style lang="scss" scoped>
.c-header {
  display: flex;
  align-items: center;
}
</style>

<docs>
  ```jsx
  <c-header />
  ```
</docs>
