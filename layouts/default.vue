<template>
  <div id="main">
    <navbar-item id="navbar"/>
    <Nuxt/>
    <footer-item id="footer"/>
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
  #navbar {
    background-color: $dark-grey;
    width: 100vw;
    display: flex;
    flex-direction: row-reverse;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0;
    z-index: 2;
  }
  @media screen and (min-width: 800px){
    #navbar {
      display: none;
    }
  }
</style>
