<template>
  <div>
    <h1>Derniers articles: </h1>
    <ul>
      <li v-for="article of articles" :key="article.slug">
        <NuxtLink :to="`/articles/${article.slug}`">
          <img :src="article.img" />
          <div>
            <h2>{{ article.title }}</h2>
            <p>{{ article.description }}</p>
          </div>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ArticlesPage",
   async asyncData({ $content, params }) {
      const articles = await $content('articles')
        .only(['title', 'description', 'img', 'slug'])
        .sortBy('createdAt', 'asc')
        .fetch()

      return {
        articles
      }
    }
}
</script>

<style>

</style>
