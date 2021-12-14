<template>
  <article>
    <div class="ArticleInfo">
      <h1>{{ article.title }}</h1>
      <p>{{ article.description }}</p>
      <img :src="require(`~/assets/images/${article.img}`)" :alt="article.alt" />
      <p>Article last updated: {{ formatDate(article.updatedAt) }}</p>
      <div class="TableOfContents">
        <nav>
          <ul>
            <li v-for="link of article.toc" :key="link.id">
              <NuxtLink :to="`#${link.id}`" :class="{ 'link2': link.depth === 2, 'link3': link.depth === 3 }">{{ link.text }}</NuxtLink>
            </li>
          </ul>
        </nav>
      </div>
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
  

  .link2 {
    color: red;
  }

  .link3 { 
    color: green;
  }

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

  .icon.icon-link {
    background-image: url('~assets/svg/icon-hashtag.svg');
    display: inline-block;
    width: 24px;
    height: 24px;
    background-size: 24px 24px;
  }

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