<template>
  <div id="accueil_main">
    <div id="sea" >
      <div id="top_layer">
        <img id="logo_main" src="@/assets/images/logo_t_home.png" alt=""/>
        <p id="helper_mobile">Explore les différentes îles pour découvrir notre liste !</p>
      </div>
      <div id="mid_layer">
        <div id="equipage_div"   class="island ">
          <NuxtLink  id="equipage_link" class="link animated" to="/equipage" >
            <img class="icon" src="@/assets/images/assets_crew.png" alt="Découvrir l'équipage !"/>
          </NuxtLink>
          <p id="equipage_text">L'équipage</p>
        </div>
        <div id="actualités_div" class="island">
          <NuxtLink   id="actualités_link" class="link animated" to="/article" >
            <img class="icon" src="@/assets/images/assets_news.png" alt="Les dernières actualités !"/>
          </NuxtLink>
          <p id="actualités_text">Les actualités</p>
        </div>
        <div id="evenements_div" class="island ">
          <NuxtLink  id="evenements_link" class="link animated"  to="/evenements" >
            <img class="icon" src="@/assets/images/assets_events.png" alt="Des infos sur les évènements à venir !"/>
          </NuxtLink>
          <p id="evenements_text">Les évènements</p>
        </div>
        <div  id="video_player_div" class="island ">
          <div class="link animated">
            <img  class="icon " v-on:click="ChangeIndex"  src="@/assets/images/assets_videos.png" alt="Pour revoir les films de campagne !"/>
          </div>
          <p id="video_player_text">Les vidéos</p>
        </div>
        <div class="island bottom " id="video_player_div_mobile">
          <p id="video_player_text_mobile">Les vidéos</p>
          <a id="video_player_svg_mobile_link" class="animated" href="https://www.youtube.com/channel/UCENnVoGO_68vCun99IBWAHg">
            <img id="icon" src="@/assets/images/assets_videos.png" alt="Pour revoir les films de campagne !"/>
          </a>
        </div>
      </div>

      <div id="video_player_media" v-on:click="ChangeIndex" >
        <div id="player_container" v-on:click="ChangeIndex">
          <VideoPlayerItem/>
        </div>
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

.icon {
  height: auto;
  width: auto;
  max-width: 100%;
  max-height: 100%;
}

#icon {
  height: 80%;
  width: 100%;
  max-width: 100%;
  max-height: 80%;
}

@media screen and (min-width: 700px) {
  #accueil_main {
    height: calc(100vh - 50px);
    width: 100%;
    #helper_mobile {
      display: none;
    }
    #sea {
      z-index: 0;
      cursor: $cursor_classic;
      height: 100%;
      width: 100%;
      background-color: var(--background-color);
      color: var(--text-color);
      justify-items: center;
      align-items: center;
      display: flex;
      flex-direction: column;



      #top_layer {
        height: 50%;
        display: flex;
        align-items: center;

      }
      #mid_layer {
        height: 50%;
        width: 60%;
        display: flex;
        flex-direction: row;
        padding-bottom: 50px;
      }

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

      #equipage_div:hover {
        #equipage_text {
          opacity: 1;
        }
      }


      #actualités_div:hover {
        #actualités_text {
          opacity: 1;
        }
      }


      #evenements_div:hover {
        #evenements_text {
          opacity: 1;
        }
      }


      #video_player_div:hover {
        #video_player_text {
          opacity: 1;
        }
      }

      p {
        font-size: 35px;
        opacity: 1;
        text-align: center;
      }

        #logo_main {
          height: auto;
          width: auto;
          max-width: 100%;
          max-height: 80%;
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
  p {
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
    background-color: var(--background-color);
    color: var(--text-color);

    #top_layer {
      padding-top: 70px;
      display: flex;
      flex-direction: column;
      align-items: center;

      #logo_main {
        animation: 3s infinite ease-in-out alternate boat;
        height: auto;
        width: auto;
        max-width: 80%;
        max-height: 80%;
        padding-bottom: 20px;
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

