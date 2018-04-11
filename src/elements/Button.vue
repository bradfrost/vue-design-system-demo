<template>
  <component class="butt">
    <button class="button">{{ value }}</button>
  </component>
</template>

<script>
/**
 * Buttons!
 */
export default {
  name: "Butt",
  status: "ready",
  release: "1.0.0",
  props: {
    /**
     * The name of the icon to display.
     */
    value: {
      required: true,
      default: "Farts",
    },
  },
}
</script>

<style lang="scss" scoped>
.button {
  background: orange;
  display: block;
  padding: 2rem;
  width: 100%;
}
</style>

<docs>
  ```jsx
  <div>
    <butt value="Buuuuuuuttttttt" />
  </div>
  ```
</docs>
