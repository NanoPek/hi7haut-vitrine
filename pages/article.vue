<template>
  <div>
    <h1>Les articles & évènements :</h1>
    <ul>
      <li v-for="article of articles" :key="article.slug">
        <NuxtLink :to="`/articles/${article.slug}`">
          <div class="article">
            <div class="imgWrapper">
              <img :src="require(`~/assets/images/${article.img}`)" />
            </div>
            <div class="text">
              <h2>{{ article.title }}</h2>
              <p>{{ article.description }}</p>
            </div>
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

<style lang="scss" scoped>

  ul {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  a {
    text-decoration: none;
  }

  h1 {
    text-align: center;
  }
  .article {
    background-color: antiquewhite;
    border-radius: 5px;
    color: black;
    display: flex;
    width: 70vw;
    height: 150px;
    justify-content: space-between;
    margin-bottom: 20px;
  }

  .text {

    width: calc(100% - 300px);
    margin-left: 10px;

    p {
      font-style: italic;
    }

  }



  .imgWrapper {

    width: 300px;
    display: flex;
    align-items: center;
    justify-content: center;

  }

  img {
    // display: block;
    max-width: 100%;
    max-height: 150px;
    object-fit: cover;
  }
</style>
