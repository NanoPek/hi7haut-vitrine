<template>
  <div id="main">
    <navbar-item id="navbar"/>
    <Nuxt/>
    <footer-item id="footer"/>
  </div>
</template>

<script>
export default {
  name: "first-page"
}
</script>

<style lang="scss" scoped>
  #main {
    overflow: hidden;
    display: flex;
    flex-direction: column;
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
    #footer {
      position: fixed;
      bottom: 0;
    }
  }
</style>
