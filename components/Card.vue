<template>
  <div class="box is-radiusless">
    <article class="media">
      <figure class="media-left">
        <div v-if="post.fields.headerImage">
          <p class="image is-128x128">
            <img :src="post.fields.headerImage.fields.file.url" alt="thumbnail">
          </p>
        </div>
        <div v-else>
          <p class="image is-128x128">
            <img src="https://bulma.io/images/placeholders/128x128.png" alt="thumbnail">
          </p>
        </div>
      </figure>
      <figure class="media-content">
        <div class="content">
          <div class="is-size-4">
            {{ post.fields.title }}
          </div>
          <div class="has-text-right">
            <small>{{ getFormattedDate(post.fields.publishedAt) }}</small>
          </div>
        </div>
      </figure>
    </article>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      require: true,
      default: () => {
        return {
          fields: {
            title: 'sample',
            publishedAt: new Date(),
            headerImage: null
          }
        }
      }
    }
  }, /* props */

  methods: {
    getFormattedDate (date) {
      const originDate = new Date(date)
      const year = originDate.getFullYear()
      const month = originDate.getMonth() + 1
      const day = originDate.getDate()
      return `${year}年${month}月${day}日`
    }
  }
}
</script>

<style scoped>
.box {
  box-shadow: 0.5em;
  margin-bottom: 10px;
}
</style>
