<template>
  <header id="template_header">
    <nav id="template_navbar">
      <ul id="list_navbar">
        <li><a>Acceuil</a></li>
        <li><a>L'équipage</a></li>
        <li><a>Actualités</a></li>
        <li><a>Évènements</a></li>
      </ul>
    </nav>
  </header>
</template>

<style lang="scss">
  #template_header {
    width: 100%;
    background-color: #141414;
    color: $text-red;
  }
  #template_navbar {
    width: 100%;
  }
  #list_navbar {
    list-style: none;
    padding: 20px 0;
    margin: 0;
  }
  ul > li {
    display: inline-block;
    margin: 0 20px;
    zoom:1;
    *display:inline; /* this fix is needed for IE7- */
  }
</style>
