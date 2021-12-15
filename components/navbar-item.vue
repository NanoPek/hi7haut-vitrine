<template>
  <header id="template_header">
    <NuxtLink to="/" >
      <img id="logo_navbar" src="@/assets/images/logo.jpg" alt=""/>
    </NuxtLink>
      <nav id="template_navbar">
        <ul id="list_navbar">
          <li><NuxtLink id="retour_acceuil" to="/" >Retour à la carte</NuxtLink></li>
          <li><NuxtLink class="NuxtLinkNavbar" to="/equipage">L'équipage</NuxtLink></li>
          <li><NuxtLink class="NuxtLinkNavbar" to="/article">Les articles</NuxtLink></li>
          <li><NuxtLink class="NuxtLinkNavbar" to="/evenements">Les évènements</NuxtLink></li>
        </ul>
      </nav>
  </header>


</template>

<script>
export default {
  name: "NavBar"
}
</script>

<style lang="scss">


  #template_header {
    width: 100%;
    background-color: $dark-grey;
    font-family: "Pirata One";
    font-size: 30px;
    display: flex;
    flex-direction: row;
    align-items: center;
    position: sticky;
    top: 0;

  }
  #logo_navbar {
    height: 60px;
    width: 60px;
    margin: 0 20px;
    cursor: $cursor_pointer;
  }
  #template_navbar {
    width: 100%;
  }
  #list_navbar {
    list-style: none;
    margin: 0;
  }
  ul > li {
    display: inline-block;
    margin: 0 20px;
    zoom:1;
    *display:inline; /* this fix is needed for IE7- */

  }

  .NuxtLinkNavbar {
    display: inline-block;
    position: relative;
    text-decoration: none;
    color: $gold;
    cursor: $cursor_pointer;
  }
  #retour_acceuil {
    display: inline-block;
    position: relative;
    text-decoration: none;
    color: $blue;
    cursor: $cursor_pointer;
  }
  #retour_acceuil:after {
    content: '';
    position: absolute;
    width: 100%;
    transform: scaleX(0);
    height: 2px;
    bottom: 0;
    left: 0;
    background-color: $blue;
    transform-origin: bottom right;
    transition: transform 0.25s ease-out;
  }
  #retour_acceuil:hover:after {
    transform: scaleX(1);
    transform-origin: bottom left;
  }

  .NuxtLinkNavbar:after {
    content: '';
    position: absolute;
    width: 100%;
    transform: scaleX(0);
    height: 2px;
    bottom: 0;
    left: 0;
    background-color: $gold;
    transform-origin: bottom right;
    transition: transform 0.25s ease-out;
  }

  .NuxtLinkNavbar:hover:after {
    transform: scaleX(1);
    transform-origin: bottom left;
  }
</style>
