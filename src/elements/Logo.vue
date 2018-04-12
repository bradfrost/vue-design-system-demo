<template>
  <component :is="type" :href="href" class="c-logo-link">
    <img class="c-logo-link__img" src='../assets/images/logo.svg' />
  </component>
</template>

<script>
/**
 * Buttons!
 */
export default {
  name: "Logo",
  status: "ready",
  release: "1.0.0",
  props: {
    /**
     * The html element name used for the component.
     */
    type: {
      type: String,
      default: "a",
    },
    href: {
      type: String,
      default: "http://google.com",
    },
  },
}
</script>

<style lang="scss" scoped>
.c-logo-link {
  display: inline-block;
  padding: 0.2rem 1rem;
  max-width: 15rem;
}
.c-logo-link__img {
  max-width: 15rem;
}
</style>

<docs>
  ```jsx
  <logo />
  ```
</docs>
