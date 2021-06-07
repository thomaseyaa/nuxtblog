<template>
  <div>
    <h1 class="text-center mt-5 mb-3">Post</h1>
    <div class="row justify-content-center">
      <div class="col-sm-6 mt-5">
        <div>
          <h2>{{ post.title}}</h2>
          <p>{{ post.body}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Nuxtblog' - this.post.title,
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
      post: {}
    }
  },
  async asyncData({ params, $http }) {
    const post = await $http.$get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
    return { post }
  }
}
</script>
