<template>
  <div id="main_equipage">
    <h1>L'équipage</h1>
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
    background-color: var(--background-color);
    color: var(--text-color);
    display: flex;
    flex-direction: column;
    padding: 0 15%;

    #bureaux {
      display: flex;
      flex-direction: column;
    }
  }
  @media screen and (max-width: 700px) {
    #main_equipage {
      margin-top: 50px;
      padding: 0 5%;
    }
  }
</style>
