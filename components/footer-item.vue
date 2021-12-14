<template>
  <footer> 
    <div class="links">
      <icon-link src="facebook.svg" alt="facebook icon" href="https://facebook.com" class="link"/>
      <icon-link src="instagram.svg" alt="instagram icon" href="https://instagram.com" class="link"/>
    </div>
    <div class="authors">
      ©
      <a href="https://www.tomorrowtides.com/nano7.html" target="_blank">CARREZ Jérémie</a>
      -
      <a href="https://www.nohehf.com" target="_blank">HINNIGER-FORAY Nohé</a>
      -
      <a href="https://www.tomorrowtides.com/nano7.html" target="_blank">Hi7Haut</a>  
    </div>
  </footer>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
  a {
    color: white;  
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

    .links {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 80px;  
    }

    .link {

      height: 30px;
      width: 30px;

    }
  }
</style>