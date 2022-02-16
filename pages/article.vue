<template>
  <div class="main_articles">
    <h1>Les dernières actualités :</h1>
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
@media screen and (min-width: 700px) {
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
    font-size: 40px;
  }
  .article {
    background-color: $gold;
    border-radius: 5px;
    color: black;
    display: flex;
    width: 70vw;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }

  .text {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

    width: calc(100% - 300px);
    margin-left: 10px;

    h2 {
      font-size: 30px;
    }

    p {
      font-style: italic;
      font-size: 20px;
    }

  }


  .imgWrapper {

    width: 300px;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    margin: 0 10px;

  }

  img {
    height: auto;
    width: auto;
    max-width: 100%;
    max-height: 90%;
  }
}

  @media screen and (max-width: 700px) {
    .main_articles {
      margin-top: 50px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .imgWrapper {

      width: 300px;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100%;

    }

    img {
      height: auto;
      width: auto;
      max-width: 100%;
      max-height: 90%;
    }
    a {
      text-decoration: none;
      color: white;
    }
    ul {
      list-style-type: none;
      padding: 0;
      margin: 0;

      li {
        width: 90%;
        margin: 10px 5%;

        .article {
          width: 100%;
          display: flex;
          flex-direction: column;
          align-items: center;

          .text {
            width: 100%;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            h2 {
              font-size: 25px;
            }
            p {
              font-size: 18px;
            }
          }
        }
      }
    }
  }
</style>
