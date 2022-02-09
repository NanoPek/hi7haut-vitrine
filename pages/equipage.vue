<template>
  <div id="main_equipage">
    <h1>Equipage</h1>
    <div id="bureaux">
      <bureau-item nom_bureau="BDE"/>
      <bureau-item nom_bureau="FOY"/>
      <bureau-item nom_bureau="BDS"/>
      <bureau-item nom_bureau="BDD"/>
      <bureau-item nom_bureau="BDA"/>

    </div>
  </div>


</template>

<script>
import BureauItem from "~/components/bureau-item";
export default {
  name: "equipage-page",
  components: {BureauItem},
}
</script>

<style lang="scss" scoped>
  #main_equipage {
    background-color: $dark-blue;
    display: flex;
    flex-direction: column;
    padding: 0 15%;
    color: $dark-white;

    #bureaux {
      display: flex;
      flex-direction: column;


    }
  }
</style>
