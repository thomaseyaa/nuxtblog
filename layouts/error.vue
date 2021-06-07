<template>
  <div>
    <h1 class="text-center mt-5 mb-3">Error</h1>
    <div class="row justify-content-center text-center">
      <div class="col-sm-6 mt-5" v-if="error.statusCode === 404">
        <p>This page doesn't exist</p>
        <b-button variant="outline-primary"><NuxtLink to="/">Back home</NuxtLink></b-button>
      </div>
      <div class="col-sm-6 mt-5" v-else>
        <p>An error occurred - {{ error.statusCode }}</p>
        <b-button variant="outline-primary"><NuxtLink to="/">Back home</NuxtLink></b-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Nuxtblog - Error',
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
  props: ['error'],
  layout: 'error'
}
</script>
