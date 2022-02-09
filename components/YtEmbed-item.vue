<template>
  <iframe :width="windowWidth/1.65" :height="windowWidth/1.65/1.84" :src="'https://www.youtube.com/embed/' + video_id " title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

</template>

<script>
export default {
  name: "YtEmbed-item",
  props: ['video_id'],
  data() {
    return {
      windowWidth: 200,
      txt: ''
    }
  },

  watch: {
    windowWidth(newWidth, oldWidth) {
      this.txt = `it changed to ${newWidth} from ${oldWidth}`;
    }
  },

  mounted() {
    this.$nextTick(() => {
      window.addEventListener('resize', this.onResize);
    })
  },

  beforeDestroy() {
    window.removeEventListener('resize', this.onResize);
  },

  methods: {
    onResize() {
      this.windowWidth = window.innerWidth
    }
  }
}
</script>

<style scoped>

</style>
