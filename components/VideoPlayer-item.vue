<template>
  <div id="VideoPlayer_main">
    <img v-on:click="forceRerender(index -1)" src="@/assets/images/left.svg"/>
    <div id="video">
      <YtEmbedItem :key="componentKey" :video_id="current_id[index]" />
    </div>
    <img v-on:click="forceRerender(index + 1)" src="@/assets/images/right.svg"/>
  </div>
</template>

<script>
import YtEmbedItem from "~/components/YtEmbed-item";
export default {
  name: "VideoPlayer-item",
  components: {YtEmbedItem},
  data() {
    return {
      index: 0,
      current_id: ['XDNyJbqmLCE','khsIOsZMAEo'],
      componentKey: 0
    }
  },
  methods: {
    forceRerender(i) {
      if (i <0) {
        this.index = this.current_id.length - 1
      } else if (i >= this.current_id.length) {
        this.index = 0
      } else {
        this.index = i
      }
      this.componentKey += 1
    }
  }
}
</script>

<style lang="scss" scoped>
  #VideoPlayer_main {
    display: flex;
    flex-direction: row;
    align-items: center;
  }
img {
  height: 50px;
  border-radius: 50%;
  background-color: $dark-grey;
  margin: 0 20px ;


}
img:hover {
  cursor: pointer;
  background-color: red;
}

</style>
