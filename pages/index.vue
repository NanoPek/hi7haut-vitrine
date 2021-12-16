<template>
  <div id="accueil_main">
    <div id="sea" >
      <div id="equipage_div"  class="island">
        <NuxtLink  id="equipage_link" class="animated" to="/equipage" >
          <img id="equipage_svg" src="@/assets/svg/palmier.svg" alt="Découvrir l'équipage !"/>
        </NuxtLink>
        <h1 id="equipage_text">L'équipage</h1>
      </div>
      <div id="actualités_div" class="island">

        <h1 id="actualités_text">Les actualités</h1>
        <NuxtLink   id="actualités_link" class="animated" to="/article" >
          <img id="actualités_svg" src="@/assets/svg/grotte.svg" alt="Les dernières actualités !"/>
        </NuxtLink>
      </div>
      <img id="logo_main" src="@/assets/images/logo_t.png" alt=""/>
      <div id="evenements_div" class="island">
        <NuxtLink  id="evenements_link" class="animated"  to="/evenements" >
          <img id="evenements_svg" src="@/assets/svg/crane.svg" alt="Des infos sur les évènements à venir !"/>
        </NuxtLink>
        <h1 id="evenements_text">Les évènements</h1>
      </div>

      <div class="island" id="video_player_div">
        <h1 id="video_player_text">Les vidéos</h1>
        <img id="video_player_svg" class="animated" v-on:click="ChangeIndex"  src="@/assets/svg/pieuvre.svg" alt="Pour revoir les films de campagne !"/>
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
  #accueil_main {
    #sea {
      z-index: 0;
      cursor: $cursor_classic;
      height: 100vh;
      width: 100%;
      background-color: $blue;
      justify-items: center;
      align-items: center;
      display: grid;
      grid-template-columns: repeat(4,1fr) 2fr repeat(4,1fr);
      grid-template-rows: repeat(2,1fr) 2fr repeat(2,1fr);

      .island {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;


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
        grid-row: 2;
        width: 100%;
        height: 100%;

        #equipage_link {
          width: 100%;
          height: 100%;
        }
      }
      #equipage_div:hover{
        #equipage_text {
          opacity: 1;
        }
      }
      #actualités_div {
        grid-column: 8;
        grid-row: 4;

        #actualités_link {
          height: 100%;
          width: 100%;
        }
      }
      #actualités_div:hover{
        #actualités_text {
          opacity: 1;
        }
      }
      #evenements_div {
        grid-column: 3;
        grid-row: 2;

        #evenements_link {
          height: 100%;
          width: 100%;
        }
      }
      #evenements_div:hover{
        #evenements_text {
          opacity: 1;
        }
      }
      #video_player_div {
        grid-column: 2;
        grid-row: 4;
      }
      #video_player_div:hover{
        #video_player_text {
          opacity: 1;
        }
      }
      h1 {
        opacity: 0;
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
</style>

