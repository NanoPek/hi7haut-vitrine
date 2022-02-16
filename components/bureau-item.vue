<template>
  <div id="main_bureau">
    <div class="upper">
      <img v-bind:src="require('@/assets/images/' + nom_bureau + '.png')" alt="logo_bureau.png">
      <h3>Lorem ipsum dolor sit amet. Qui porro perspiciatis ad nihil possimus ea placeat maiores qui saepe blanditiis et quibusdam praesentium sit internos numquam ad repudiandae autem. Et sunt rerum eum minima voluptatem est dicta exercitationem aut sequi dolorem. Rem cumque neque et modi magni et veniam mollitia est quae quod. Et neque dignissimos cum earum iure eos perspiciatis natus sed esse voluptatem vel laboriosam explicabo eum dolor numquam qui dolores deleniti.</h3>
    </div>
    <membres-item v-bind:nom_bureau="nom_bureau"/>
  </div>
</template>

<script>
import MembresItem from "~/components/membres-item";
export default {
  name: "bureau-item",
  components: {MembresItem},
  props: ['nom_bureau']
}
</script>

<style lang="scss" scoped>
  #main_bureau {
    display: flex;
    flex-direction: column;
    .upper {
      display: flex;
      flex-direction: row;
      img {
        width: 100px;
        height: auto;
        margin: 0 20px;
      }
  }
    .lower {
      display: flex;
      flex-direction: row;
      justify-content: space-evenly;
      img {
        width: 200px;
      }
    }
  }

  @media screen and (max-width: 700px) {
    .upper {
      flex-direction: column !important;
      align-items: center;
    }
  }
</style>
