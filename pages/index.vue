<template>
  <div id="accueil_main">
    <div id="sea" >
      <NuxtLink  id="equipage_link" class="island" to="/equipage" >
        <img id="equipage_svg" src="@/assets/svg/palmier.svg" alt="Découvrir l'équipage !"/>
      </NuxtLink>
      <img id="logo_main" src="@/assets/images/logo_t.png" alt=""/>
      <NuxtLink   id="actualités_link" class="island" to="/article" >
        <img id="actualités_svg" src="@/assets/svg/grotte.svg" alt="Les dernières actualités !"/>
      </NuxtLink>
      <NuxtLink  id="evenements_link" class="island"  to="/evenements" >
        <img id="evenements_svg" src="@/assets/svg/crane.svg" alt="Des infos sur les évènements à venir !"/>
      </NuxtLink>
      <div class="island" id="video_player_div">
        <img v-on:click="ChangeIndex" id="video_player_svg" src="@/assets/svg/pieuvre.svg" alt="Pour revoir les films de campagne !"/>
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
// import VideoPlayerItem from "~/components/VideoPlayer-item";


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
        animation-name: appearing, zoom;
        animation-duration: 2000ms, 2000ms;
        animation-delay: 2000ms, 4000ms; /* add this */
        animation-timing-function: ease-in, ease-in-out;
        animation-iteration-count: 1, infinite;
        animation-direction: normal, alternate;
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
      #video_player_div {
        grid-column: 2;
        grid-row: 5;
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

