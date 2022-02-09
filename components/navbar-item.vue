<template>
  <header id="template_header">
    <NuxtLink to="/" >
      <img id="logo_navbar" src="@/assets/images/logo.jpg" alt=""/>
    </NuxtLink>
      <nav id="template_navbar">
        <ul id="list_navbar">
          <li><NuxtLink id="retour_acceuil" to="/" >Retour à la carte</NuxtLink></li>
          <li><NuxtLink class="NuxtLinkNavbar" to="/equipage">L'équipage</NuxtLink></li>
          <li><NuxtLink class="NuxtLinkNavbar" to="/article">Les Actualités</NuxtLink></li>
          <li><NuxtLink class="NuxtLinkNavbar" to="/evenements">Les Évènements</NuxtLink></li>
        </ul>
      </nav>
    <div id="mobile_menu_div" @click="toggleMobileMenu">
      <div class="bar1"></div>
      <div class="bar2"></div>
      <div class="bar3"></div>
      <ul class="mobile-menu">
        <li><NuxtLink id="retour_acceuil_mobile" to="/" >Carte</NuxtLink></li>
        <li><NuxtLink class="NuxtLinkNavbar" to="/equipage">L'équipage</NuxtLink></li>
        <li><NuxtLink class="NuxtLinkNavbar" to="/article">Les Actualités</NuxtLink></li>
        <li><NuxtLink class="NuxtLinkNavbar" to="/evenements">Les Évènements</NuxtLink></li>
      </ul>
    </div>
    <LinksItem/>
  </header>


</template>

<script>
import LinksItem from "~/components/links-item";
export default {
  name: "NavBar",
  components: {LinksItem},
  methods: {
    toggleMobileMenu() {
      this.toggled = !this.toggled;
    }
  }
}

</script>

<style lang="scss">

@media screen and (min-width: 800px) {
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
    height: 50px;
    width: 50px;
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
    color: $green;
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
    background-color: $green;
    transform-origin: bottom right;
    transition: transform 0.25s ease-out;
  }

  .NuxtLinkNavbar:hover:after {
    transform: scaleX(1);
    transform-origin: bottom left;
  }
  #mobile_menu_div {
    display: none;
  }
}
@media screen and (max-width: 800px) {
  #logo_navbar {
    display: none;
  }

  #template_navbar {
    display: none;
  }


  #mobile_menu_div div {
    width: 35px;
    height: 3px;
    background-color: white;
    margin: 6px 0;
    transition: 0.4s;
  }

  .mobile-menu {
    display: none;
    position: absolute;
    top: 50px;
    left: 0;
    height: calc(100vh - 50px);
    width: 100%;
  }

  .open .mobile-menu {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
  }

  .mobile-menu li {
    margin-bottom: 10px;
  }





  .open .bar1 {
    -webkit-transform: rotate(-45deg) translate(-6px, 6px);
    transform: rotate(-45deg) translate(-6px, 6px);
  }

  .open .bar2 {
    opacity: 0;
  }

  .open .bar3 {
    -webkit-transform: rotate(45deg) translate(-6px, -8px);
    transform: rotate(45deg) translate(-6px, -8px);
  }
}
</style>
