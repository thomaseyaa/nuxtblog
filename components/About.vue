<template>
  <div>
    <h1 class="text-center mt-5 mb-3">About</h1>
    <div class="row justify-content-center">
      <div class="col-sm-6 mt-5">
        <div>
          <p>Nextblog is an journal website displaying information about Nuxt framework. Nuxt is based on a powerful modular architecture. You can choose from over 50 modules to make your development faster and easier. You don't have to reinvent the wheel to get the PWA benefits, add Google Analytics to your page, or generate a sitemap.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Nuxtblog - About',
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
}
</script>
