<template>
  <a :href="href" target="_blank">
    <img :src="require(`~/assets/svg/${src}`)" :alt="alt" >
  </a>
</template>

<script>
export default {
  props: {
      src: {
        type: String,
        required: true,
      },
      alt: {
        type: String,
        required: true,
      },
      href: {
        type: String,
        required: true,
      },
  }
}
</script>

<style lang="scss" scoped>
</style>