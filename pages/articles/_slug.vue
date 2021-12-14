<template>
  <article>
    <div class="ArticleInfo">
      <h1>{{ article.title }}</h1>
      <p>{{ article.description }}</p>
      <img :src="article.img" :alt="article.alt" />
      <p>Article last updated: {{ formatDate(article.updatedAt) }}</p>
    </div>

    <nuxt-content :document="article" />
  </article>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const article = await $content('articles', params.slug).fetch()

      return { article }
    },

    methods: {
      formatDate(date) {
        const options = { year: 'numeric', month: 'long', day: 'numeric' }
        return new Date(date).toLocaleDateString('en', options)
      }
    },

  }
</script>

<style scoped>
  .ArticleInfo {
    display: flex;
    flex-direction: column;
  }

  h1 { 
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  }

  img {
    
    max-height: 200px;
  
  }
</style>

<style>

  .nuxt-content { 
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }

  .nuxt-content h2 {
    font-weight: bold;
    font-size: 28px;
  }
  .nuxt-content h3 {
    font-weight: bold;
    font-size: 22px;
  }
  .nuxt-content p {
    margin-bottom: 20px;
    font-size: medium;
    font-weight: 400;
  }
</style>