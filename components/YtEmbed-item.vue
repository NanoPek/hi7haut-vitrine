<template>
  <iframe width="1160" height="630" :src="'https://www.youtube.com/embed/' + video_id " title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

</template>

<script>
export default {
  name: "YtEmbed-item",
  props: ['video_id']
}
</script>

<style scoped>

</style>
