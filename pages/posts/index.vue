<template>
  <div>
    <h1 class="text-center mt-5 mb-3">Posts</h1>
    <div class="row justify-content-center">
      <div class="col-sm-6 mt-5">
        <div v-if="posts.length">
          <b-card class="mb-4" v-for="post of posts" v-key="post.id">
            <b-card-text>{{ post.title }}</b-card-text>
            <nuxt-link :to="`/posts/${post.id}`">Read</nuxt-link>
          </b-card>
        </div>

        <div v-else>
          <b-card class="mb-4" v-for="post of posts" v-key="post.id">
            <b-card-text>No posts.</b-card-text>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Nuxtblog - Posts',
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        {
          hid: 'Description',
          name: 'Description',
          content: 'My description'
        }
      ],
      link: [{ rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }]
    }
  },
  data() {
    return {
      posts: []
    }
  },
  async asyncData({ $http }) {
    const posts = await $http.$get("https://jsonplaceholder.typicode.com/posts");
    return { posts }
  }
}
</script>
