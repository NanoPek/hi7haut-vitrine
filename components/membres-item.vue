<template >
  <div id="main_membres">
    <div v-for="client in images" :key="client.pathLong">
      <img :src="client.pathLong"/>
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
        this.importAll(require.context('@/assets/images/BDE/', true, /\.png$/));
        break;
      case "BDS":
        this.importAll(require.context('@/assets/images/BDS/', true, /\.png$/));
        break;
      case "BDA":
        this.importAll(require.context('@/assets/images/BDA/', true, /\.png$/));
        break;
      case "FOY":
        this.importAll(require.context('@/assets/images/FOY/', true, /\.png$/));
        break;
      case "BDD":
        this.importAll(require.context('@/assets/images/BDD/', true, /\.png$/));
        break;
    }
  },

  methods: {
    importAll(r) {
      r.keys().forEach(key => (this.images.push({ pathLong: r(key), pathShort: key })));
    },
  },
};
</script>

<style lang="scss" scoped>
  #main_membres {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-evenly;
    img {
      width: 200px;
    }
  }
</style>
