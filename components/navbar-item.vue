<template>
  <header id="template_header" class="header">
    <NuxtLink id="logo_nuxlink" to="/" >
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
    <div id="mobile_menu_div" :class="['container', { 'open': toggled }]" @click="toggleMobileMenu">
      <div :class="['bar1', { 'open': toggled }]"></div>
      <div :class="['bar2', { 'open': toggled }]"></div>
      <div :class="['bar3', { 'open': toggled }]"></div>
      <ul :class="['mobile-menu', { 'open': toggled }]">
        <li><NuxtLink id="retour_acceuil_mobile" to="/" >Carte</NuxtLink></li>
        <li><NuxtLink class="NuxtLinkNavbar" to="/equipage">L'équipage</NuxtLink></li>
        <li><NuxtLink class="NuxtLinkNavbar" to="/article">Les Actualités</NuxtLink></li>
        <li><NuxtLink class="NuxtLinkNavbar" to="/evenements">Les Évènements</NuxtLink></li>
        <li><img id="logo_navbar_li" src="@/assets/images/logo.jpg" alt=""/></li>
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
  data() {
    return {
      toggled: false
    }
  },
  methods: {
    toggleMobileMenu() {
      this.toggled = !this.toggled;
    }
  }
}

</script>

<style lang="scss">

@media screen and (min-width: 700px) {
  .header {
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
@media screen and (max-width: 700px) {

  .links {
    display: none !important;
  }

  #logo_navbar {
    height: 50px;
    width: 50px;
    margin: 0 20px;
  }

  .header {
    background-color: $dark-grey;
    width: 100%;
    display: flex;
    flex-direction: row ;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0;
    z-index: 2;
  }

  #template_navbar {
    display: none;
  }
  #mobile_menu_div div {
    width: 35px;
    height: 3px;
    background-color: white;
    margin: 6px 20px;
    transition: 0.4s;
  }

  .mobile-menu {
    display: none;
    position: absolute;
    top: 32px;
    left: 0;
    height: calc(100vh - 32px);
    width: 100%;
  }

  .open .mobile-menu {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    background-color: $dark-grey;
    padding: 30px 0 0 0 ;
  }

  .mobile-menu li {
    display: inline-block;
    margin-bottom: 10px;
    zoom:1;
    *display:inline-block; /* this fix is needed for IE7- */
    font-size: 40px;
  }
  #logo_navbar_li {
    height: 100%;
    width: 100%;
  }

  .NuxtLinkNavbar {
    display: inline-block;
    position: relative;
    text-decoration:  underline;
    color: $green;
  }

  #retour_acceuil_mobile {
    display: inline-block;
    position: relative;
    text-decoration: underline;
    color: $blue;
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
