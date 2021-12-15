<template>
  <div id="accueil_main">
    <NuxtLink class="island" id="equipage_link" to="/equipage" >
      <img id="equipage_svg" src="@/assets/svg/palmier.svg" alt="Découvrir l'équipage !"/>
    </NuxtLink>
    <img id="logo_main" src="@/assets/images/logo_t.png" alt=""/>
    <NuxtLink  class="island" id="actualités_link" to="/article" >
      <img id="actualités_svg" src="@/assets/svg/grotte.svg" alt="Les dernières actualités !"/>
    </NuxtLink>
    <NuxtLink  class="island" id="evenements_link" to="/evenements" >
      <img id="evenements_svg" src="@/assets/svg/crane.svg" alt="Les dernières actualités !"/>
    </NuxtLink>
  </div>

</template>

<script>
// import VideoPlayerItem from "~/components/VideoPlayer-item";


export default {
  name: 'IndexPage',
  layout: 'firstpage',
  // components: {VideoPlayerItem},
}

</script>

<style lang="scss" scoped>

@keyframes boat {
  0% {
    transform: rotate(0deg);

  }

  25% {
    transform: rotate(-20deg);

  }

  75% {
    transform: rotate(20deg);

  }
}
@keyframes zoom {
  from {
    transform: scale(1);
  }
  to {
    transform: scale(0.8);
  }
}
  #accueil_main {
    cursor: $cursor_classic;
    height: 100vh;
    width: 100%;
    background-color: $blue;
    display: grid;
    grid-template-columns: repeat(4,1fr) 2fr repeat(4,1fr);
    grid-template-rows: repeat(2,1fr) 2fr repeat(2,1fr);
    justify-items: center;
    align-items: center;
    .island {
      width: 100%;
      height: 100%;
      animation: 2s infinite ease-in-out alternate-reverse zoom;
    }
    .island:hover {
      animation-duration: 0.75s;
      cursor: $cursor_pointer;

    }
    #equipage_link {
      grid-column: 6;
      grid-row: 2;
    }
    #actualités_link {
      grid-column: 8;
      grid-row: 4;
    }
    #evenements_link {
      grid-column: 3;
      grid-row: 3;
    }
    #logo_main {
      grid-column: 5;
      grid-row: 3;
      width: 100%;
      height: 100%;
    }
    #logo_main:hover {
      animation: 3s infinite ease-in-out alternate boat;

    }
  }
</style>

