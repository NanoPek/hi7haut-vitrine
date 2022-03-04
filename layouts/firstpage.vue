<template>
  <div id="main">
    <navbar-item id="navbar"/>
    <ThemeButton class="button"/>
    <Nuxt/>
    <footer-item id="footer"/>
  </div>
</template>

<script>
export default {
  name: "first-page",
}
</script>

<style lang="scss" scoped>
  #main {
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }
@media screen and (max-width: 700px) {
  .button {
    display: none;
  }
}
  @media screen and (min-width: 700px){
    #navbar {
      display: none;
    }
    #footer {
      position: fixed;
      bottom: 0;
    }
    .button {
      position: absolute;
      right: 20px;
      top: 20px;
    }
  }
</style>
