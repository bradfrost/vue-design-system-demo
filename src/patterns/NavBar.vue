<template>
  <component :is="type" class="c-primary-nav">
    <ul class="c-primar-nav__list">
      <li class="c-primary-nav__item" v-for="item in navItems">
          <a :href="item.href" class="c-primary-nav__link {active: localActive === item.component}" v-html="item.name"></a>
      </li>
    </ul>
  </component>
</template>

<script>
/**
 * Used as main page navigation in templates.
 */
export default {
  name: "NavBar",
  status: "ready",
  release: "1.0.0",
  model: {
    prop: "active",
  },
  props: {
    /**
     * The html element name used for the nav bar.
     */
    type: {
      type: String,
      default: "nav",
    },
    /**
     * State which tab is active when initiated (using name of the component).
     */
    active: {
      required: true,
      type: String,
    },
    /**
     * Menu items to be displayed on the nav bar.
     */
    navItems: {
      required: true,
      type: Array,
    },
  },
  computed: {
    localActive: {
      get() {
        return this.active
      },
      set(val) {
        this.$emit("input", val)
      },
    },
  },
}
</script>

<style lang="scss" scoped>
/**
 * Navigation tag
 */
.c-primary-nav {
  display: none;

  &--is-active {
    display: block;
    position: absolute;
    padding: 1em 2em;
    top: 67px;
    right: 0;
    box-shadow: -3px 3px 5px -2px rgba(0, 0, 0, 0.2);
    z-index: 2;
    background: #fff;
  }

  @media all and (min-width: 56rem) {
    display: block;
    margin-right: 1rem;
  }
}

/**
 * Nav List
 */
.c-primary-nav__list {
  display: none;

  @media all and (min-width: 56rem) {
    display: flex;
  }

  .c-primary-nav--is-active & {
    display: block;
  }
}

/**
 * Nav Links
 */
.c-primary-nav__link {
  font-weight: bold;
  display: block;
  padding: 1rem;
}
</style>

<docs>
  ```jsx
  <nav-bar active="Dashboard" :navItems="[
    {name: 'Dashboard', component: 'Dashboard', href: '/'},
    {name: 'Posts', component: 'Posts', href: '/posts'},
    {name: 'Users', component: 'Users', href: '/users'},
    {name: 'Settings', component: 'Settings', href: '/settings'}
  ]"/>
  ```
</docs>
