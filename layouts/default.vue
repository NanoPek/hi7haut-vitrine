<template>
  <div id="main">
    <navbar-item />
    <Nuxt/>
    <footer-item />
  </div>
</template>

<script>
export default {
  name: 'Default-Template',
}
</script>
<style lang="scss" scoped>
  #main {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    min-height: 100vh;
    cursor: $cursor_classic;
  }
</style>
