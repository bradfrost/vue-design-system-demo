<template>
  <component :is="type" class="demo">
    <c-header />
    <wrapper>
      <heading level="h1">YOOOO</heading>
      <text-style><a href="https://vueds.com">Vue Design System</a> is an open-source tool for building design systems with Vue.js. It provides you and your team a set of organized tools, patterns &amp; practices. It works as the foundation for your application development.</text-style>

    </wrapper>
  </component>
</template>

<script>
/**
 * Shows how to layout and structure a home page.
 */
export default {
  name: "Demo",
  status: "deprecated",
  release: "1.0.0",
  metaInfo: {
    title: "Vue Design System",
    htmlAttrs: {
      lang: "en",
    },
  },
  props: {
    /**
     * The html element name used for the component.
     */
    type: {
      type: String,
      default: "div",
    },
  },
}
</script>

<style lang="scss" scoped>
// Local component variables
$color-template-background: $color-rich-black;
$color-template-background-top: tint($color-template-background, 5%);
$color-template-background-bottom: shade($color-template-background, 5%);
$color-template-text: #000;
$color-template-link: $color-bleu-de-france;

.demo {
  @include reset;
  @include inset-space($space-base);
  min-height: $space-xx-large * 4;
  text-align: center;
  position: relative;
  float: left;
  height: 100%;
  width: 100%;
  @media #{$media-query-large} {
    // This is how you’d use design tokens with media queries
  }
  .heading {
    color: $color-template-text;
  }
  .text-style {
    color: $color-template-text;
  }
  .text-link {
    color: $color-template-link;
  }
  .wrapper {
    max-width: $space-xx-large * 4.5;
    transform: translateX(-50%) translateY(-50%);
    position: absolute;
    left: 50%;
    top: 50%;
  }
  a {
    font-family: $font-family-text;
    color: $color-bleu-de-france;
    text-decoration: underline;
  }
}
</style>

<docs>
  ```jsx
  <demo />
  ```
</docs>
