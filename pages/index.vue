<template>
  <div id="accueil_main">
    <div id="sea" >
      <div id="logo_main_div">
        <img id="logo_main" src="@/assets/images/logo_t.png" alt=""/>
        <h1 id="helper_mobile">Explore les différentes îles pour découvrir notre liste !</h1>
      </div>
      <div id="equipage_div"   class="island ">
        <NuxtLink  id="equipage_link" class="animated" to="/equipage" >
          <img id="equipage_svg" src="@/assets/svg/palmier.svg" alt="Découvrir l'équipage !"/>
        </NuxtLink>
        <h1 id="equipage_text">L'équipage</h1>
      </div>
      <div id="actualités_div" class="island">

        <NuxtLink   id="actualités_link" class="animated" to="/article" >
          <img id="actualités_svg" src="@/assets/svg/grotte.svg" alt="Les dernières actualités !"/>
        </NuxtLink>
        <h1 id="actualités_text">Les actualités</h1>

      </div>
      <div id="evenements_div" class="island ">
        <NuxtLink  id="evenements_link" class="animated"  to="/evenements" >
          <img id="evenements_svg" src="@/assets/svg/crane.svg" alt="Des infos sur les évènements à venir !"/>
        </NuxtLink>
        <h1 id="evenements_text">Les évènements</h1>
      </div>

      <div class="island " id="video_player_div">
        <img id="video_player_svg" class="animated" v-on:click="ChangeIndex"  src="@/assets/svg/pieuvre.svg" alt="Pour revoir les films de campagne !"/>
        <h1 id="video_player_text">Les vidéos</h1>

      </div>
      <div class="island bottom " id="video_player_div_mobile">
        <h1 id="video_player_text_mobile">Les vidéos</h1>
        <a id="video_player_svg_mobile_link" class="animated" href="https://www.youtube.com/channel/UCENnVoGO_68vCun99IBWAHg">
          <img id="video_player_svg_mobile" src="@/assets/svg/pieuvre.svg" alt="Pour revoir les films de campagne !"/>
        </a>
      </div>
    </div>
    <div id="video_player_media" v-on:click="ChangeIndex" >
      <div id="player_container" v-on:click="ChangeIndex">
        <VideoPlayerItem/>
      </div>
    </div>

  </div>

</template>

<script>


import VideoPlayerItem from "~/components/VideoPlayer-item";
export default {
  name: 'IndexPage',
  components: {VideoPlayerItem},
  layout: 'firstpage',
  data() {
    return {
      MediaIsOn : false
    }
  },
  methods: {
    ChangeIndex() {
      if (this.MediaIsOn) {
        document.getElementById('video_player_media').style.zIndex = -1
        this.MediaIsOn = false
      } else {
        document.getElementById('video_player_media').style.zIndex = 1
        this.MediaIsOn = true
      }
    }
  }
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
@keyframes appearing {
  from {
    transform: scale(0);
  }
  to {
    transform: scale(1);
  }
}
@media screen and (min-width: 700px) {
  #accueil_main {
    #helper_mobile {
      display: none;
    }
    #sea {
      z-index: 0;
      cursor: $cursor_classic;
      height: calc(100vh - 50px);
      width: 100%;
      background-color: $blue;
      justify-items: center;
      align-items: center;
      display: grid;
      grid-template-columns: repeat(4, 1fr) 2fr repeat(4, 1fr);
      grid-template-rows: 2fr repeat(3, 1fr);

      .island {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;


      }

      .animated {
        animation: 2s zoom alternate ease-in-out infinite;
      }

      .animated:hover {
        animation-duration: 0.75s;
        cursor: $cursor_pointer;
      }

      #equipage_div {
        grid-column: 6;
        grid-row: 3;
        width: 100%;
        height: 100%;

        #equipage_link {
          width: 100%;
          height: 100%;
        }
      }

      #equipage_div:hover {
        #equipage_text {
          opacity: 1;
        }
      }

      #actualités_div {
        grid-column: 7;
        grid-row: 2;

        #actualités_link {
          height: 100%;
          width: 100%;
        }
      }

      #actualités_div:hover {
        #actualités_text {
          opacity: 1;
        }
      }

      #evenements_div {
        grid-column: 4;
        grid-row: 3;

        #evenements_link {
          height: 100%;
          width: 100%;
        }
      }

      #evenements_div:hover {
        #evenements_text {
          opacity: 1;
        }
      }

      #video_player_div {
        grid-column: 3;
        grid-row: 2;
      }

      #video_player_div:hover {
        #video_player_text {
          opacity: 1;
        }
      }

      h1 {
        opacity: 1;
        text-align: center;
      }

      #logo_main_div {
        grid-column: 5;
        grid-row: 1;
        width: 100%;
        height: 100%;
        #logo_main {
          width: 100%;
          height: 100%;
        }

      }

      #logo_main:hover {
        animation: 3s infinite ease-in-out alternate boat;

      }
    }


    #video_player_media {
      position: absolute;
      z-index: -1;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;

      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;

      #player_container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        background-color: rgba(57, 57, 57, 0.75);
      }
    }
  }


  #video_player_div_mobile {
    display: none !important;
  }
}

@media screen and (max-width: 700px) {
  h1 {
    font-size: 30px;
    text-align: center;
  }

  #video_player_div {
    display: none !important;
  }

  #acceuil_main {
    height: 100vh;
    width: 100vw;
    overflow: hidden;
  }

  #sea {
    z-index: 0;
    display: flex;
    flex-direction: column;
    background-color: $blue;
    #logo_main_div {
      height: 300px;
      width: 100vw;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 100px 0 50px 0;
      h1 {
        color: $gold;
        text-shadow: 2px 2px 4px #000;
      }

      #logo_main {
        animation: 3s infinite ease-in-out alternate boat;
        height: 100%;
      }
    }

    .bottom {
      flex-direction: column-reverse !important;
    }

    .island {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      margin: 20px 0;

      .animated {
        animation: 2s zoom alternate ease-in-out infinite;
        width: 50%;
      }


    }
  }
  #video_player_media {
    display: none;
  }


}
</style>

