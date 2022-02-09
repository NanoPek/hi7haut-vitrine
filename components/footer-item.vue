<template>
  <footer>
    <LinksItem/>
    <div class="authors">
      ©
      <a href="https://github.com/NanoPek" target="_blank">CARREZ Jérémie</a>
      -
      <a href="https://www.nohehf.com" target="_blank">HINNIGER-FORAY Nohé</a>
      -
      <a href="https://www.facebook.com/Hi7Haut" target="_blank">Hi7Haut</a>
    </div>
  </footer>
</template>

<script>
import LinksItem from "~/components/links-item";
export default {
  components: {LinksItem}
}
</script>

<style lang="scss" scoped>
  a {
    color: white;
    cursor: $cursor_pointer;
  }
  footer {
    display: flex;
    align-items: center;
    justify-content: space-around;
    height: 50px;
    width: 100%;
    left: 0;
    bottom: 0;
    background-color: $dark-grey;
    color: white;
    text-align: center;


  }
</style>
