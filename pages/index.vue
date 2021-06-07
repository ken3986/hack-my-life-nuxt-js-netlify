<template>
  <div>
    <Card v-for="(post, index) in posts" :key="index" :post="post" />
  </div>
</template>

<script>
import Card from '@/components/Card.vue'
import sdkClient from '@/plugins/contentful.js'

export default {
  name: 'HomePage',

  components: {
    Card
  },

  async asyncData ({ env }) {
    let posts = []
    await sdkClient.getEntries({
      content_type: 'blogPost',
      order: '-fields.publishedAt'
    }).then((res) => {
      posts = res.items
    }).catch(console.error)
    return { posts }
  },

  data () {
    return {
      posts: [
        {
          fields: {
            title: 'これはテストです。',
            publishedAt: new Date()
          }
        },
        {
          fields: {
            title: 'これはテスト２です。',
            publishedAt: new Date()
          }
        }
      ]
    }
  }
}
</script>
