<template>
  <div id="accueil_main">
    <img id="logo_main" src="@/assets/images/logo_t.png" alt=""/>

  </div>

</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style lang="scss" scoped>
  #accueil_main {
    height: 100vh;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    background-image: url("@/assets/images/beach.jpg");
    background-size: cover;
    background-position: bottom;

    #logo_main {
      height: 819px;
    }
  }

</style>

