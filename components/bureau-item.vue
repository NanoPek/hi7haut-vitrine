<template>
  <div id="main_bureau">
    <div class="upper">
      <img v-bind:src="require('@/assets/images/' + nom_bureau + '.png')" alt="BDx.png">
      <h3>Lorem ipsum dolor sit amet. Qui porro perspiciatis ad nihil possimus ea placeat maiores qui saepe blanditiis et quibusdam praesentium sit internos numquam ad repudiandae autem. Et sunt rerum eum minima voluptatem est dicta exercitationem aut sequi dolorem. Rem cumque neque et modi magni et veniam mollitia est quae quod. Et neque dignissimos cum earum iure eos perspiciatis natus sed esse voluptatem vel laboriosam explicabo eum dolor numquam qui dolores deleniti.</h3>
    </div>
    <div class="lower">
      <img src="@/assets/images/1.png">
      <img src="@/assets/images/2.png">
      <img src="@/assets/images/3.png">
    </div>
  </div>
</template>

<script>
export default {
  name: "bureau-item",
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
</style>
