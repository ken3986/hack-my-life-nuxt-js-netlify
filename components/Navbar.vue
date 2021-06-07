<template>
  <b-navbar class="is-info">
    <template slot="brand">
      <b-navbar-item :to="{ path: '/' }" tag="router-link">
        <strong class="is-size-3-desktop">Sample Blog</strong>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<script>
export default {
  name: 'Navbar',

  data () {
    return {
      test: 'test'
    }
  }, /* data */

  computed: {

  }, /* computed */

  mounted () {

  }, /* mounted */

  methods: {

  } /* methods */

  // watch: {

  // } /* watch */
}
</script>

<style>

</style>
