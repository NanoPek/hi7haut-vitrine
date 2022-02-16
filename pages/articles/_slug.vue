<template>
  <article class="Article">
    <div class="ArticleInfo">
      <h1>{{ article.title }}</h1>
      <p id="description">{{ article.description }}</p>
      <div id="image_wrapper">
        <img :src="require(`~/assets/images/${article.img}`)" :alt="article.alt" />
      </div>
      <p>Article last updated: {{ formatDate(article.updatedAt) }}</p>
    </div>

    <nuxt-content id="content" :document="article" />
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

<style  lang="scss" scoped>

.Article {
  width: 70%;
}


  .ArticleInfo {
    display: flex;
    flex-direction: column;
  }

  h1 {
    font-size: 50px;
    font-weight: bold;
  }

  p {
    font-size: 20px;
    margin: 0;
  }
  #description {
    font-size: 30px;
  }
  #image_wrapper {
    margin: 20px 0;

    img {
      height: auto;
      width: auto;
      max-width: 100%;
      max-height: 100%;
    }
  }

  .TableOfContents {
    display: flex;
    flex-direction: column;
    justify-content: center;
    font-size: 40px;
    margin: 20px 0;

    ul {
      display: flex;
      flex-direction: column;
      margin: 0;
    }

    .link2 {
      color: $blue;
      font-size: 30px;
    }

    .link3 {
      color: $green;
      margin-left: 50px;
      font-size: 20px;
    }
  }
</style>

<style>

  .icon.icon-link {
    display: none;
  }

  .nuxt-content {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin-bottom: 100px;
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
    font-size: 18px;
    font-weight: 400;
  }

  @media screen and (max-width: 700px) {
    .Article {
      width: 90% !important;
    }

  }
</style>
