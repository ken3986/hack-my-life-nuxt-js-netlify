<template>
  <div>
    <Card v-for="(post, index) in posts" :key="index" :post="post" />
  </div>
</template>

<script>
import Card from '@/components/Card.vue'
// import sdkClient from '@/plugins/contentful.js'
import { mapState } from 'vuex'

export default {
  name: 'HomePage',

  components: {
    Card
  },

  computed: {
    ...mapState(['posts'])
  }

}
</script>
