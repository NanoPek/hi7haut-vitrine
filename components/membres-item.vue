<template >
  <div id="main_membres">
    <div id="displayer_membres" v-for="client in images" :key="client.pathLong">
      <img :src="client.pathLong"/>
      <div class="name">{{client.name}}</div>
    </div>
  </div>


</template>

<script>
export default {
  name: 'membres-item',
  props: ['nom_bureau'],
  data() {
    return {
      images: [],
    };
  },

  mounted() {
    switch (this.nom_bureau) {
      case "BDE":
        this.importAll(require.context('@/assets/images/PP_Hi7Haut/BDE/500/', true, /\.png$/));
        break;
      case "BDS":
        this.importAll(require.context('@/assets/images/PP_Hi7Haut/BDS/500/', true, /\.png$/));
        break;
      case "BDA":
        this.importAll(require.context('@/assets/images/PP_Hi7Haut/BDA/500/', true, /\.png$/));
        break;
      case "FOY":
        this.importAll(require.context('@/assets/images/PP_Hi7Haut/FOY/500/', true, /\.png$/));
        break;
      case "BDD":
        this.importAll(require.context('@/assets/images/PP_Hi7Haut/BDD/500/', true, /\.png$/));
        break;
    }
  },

  methods: {
    importAll(r) {
      r.keys().forEach(key => (this.images.push({ pathLong: r(key), pathShort: key ,name: key.replace('./','').replace(/\.[a-z]*/,'').replace(/_[A-z]*/,'')})));
    },
  },
};
</script>

<style lang="scss" scoped>
  #main_membres {
    max-width: 100vw;
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    align-items: center;
    justify-content: center;
    img {
      width: 200px;
    }
  }
  #displayer_membres {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 10px;
  }
  .name{
    color: white;
    font-size: 20px;
  }
</style>
