<template>
  <div id="main_bureau">
    <div class="upper">
      <h1>{{nom_bureau}}</h1>
      <div>
        <h3 v-if="isBDE(nom_bureau)">Chers moussaillons, préparez-vous à rencontrer nos pirates du BDE, prêts à braver mers et tempêtes pour des campagnes mémorables ! Mais avant tout, notre équipage s’engage à animer la vie associative tout au long de l’année 2022-2023.
          <br>Il nous tient notamment à cœur d’entretenir la diversité des clubs de l’N7, et d’encourager la création de nouveaux. Nous souhaitons que chaque moussaillon trouve chaussure à son pied, ou plutôt… crochet à sa main !
          <br>Nous comptons vous faire vivre des aventures dignes des plus grands pirates, et ce dès cette semaine de campagne qui s’annonce riche en surprises. Nous vous attendons nombreux à tous nos événements. Ne manquez pas notre chasse au trésor organisée dans Toulouse !
          <br>En espérant vous voir embarquer avec nous pour des aventures piratesques !</h3>
        <h3 v-else-if="isBDS(nom_bureau)">Le Bureau des Sports de Hi7 Haut vous emmènera à la conquête de nouvelles mers et à la recherche du plus précieux trésor qu’est le plaisir du sport. Un bureau dynamique axé sur la diversité sera notre cap. Avec la découverte d’un sport par mois et un décathlon géant sur toute l’année à l’N7, vous trouverez votre voie.
          <br>L’esprit combatif est pour notre équipage une qualité incontournable, c’est pourquoi un tournoi Urban Soccer sera organisé avec des lots à remporter. Voulant confirmer nos talents de sportifs et d’ingénieurs, une compétition de descente en kayak entre écoles se déroulera a posteriori de la conception de votre authentique kayak. De même du côté e-sport, un tournoi interne s'organisera au B00 et, pour les plus aguerris, une compétition au niveau des grandes écoles.
          <br>Le BDS compte fournir la logistique d’abordage pour supporter nos équipes aux Coupes de France. Nous voulons hisser au plus haut nos valeurs et participer à des courses solidaires. Un partenariat avec Basic Fit est envisagé pour éviter que vous ne viriez de bord après les soirées concoctées par nos compatriotes du Foy’. Enfin, embarquez dans nos WES (Week-End Sport) dans les Pyrénées pour défier les sommets lors de randonnées culturelles et sur la côte basque à la conquête des vagues.</h3>
        <h3 v-else-if="isBDA(nom_bureau)">Cette année, le BDA Hi7Haut vous présente un art inédit : la piraterie !
          <br>Quoi de mieux pour commencer les campagnes que des ateliers pirates en tout genre allant de la confection de tricornes & coffres à l’apprentissage de la chorée de liste, le tout  dans la joie et la bonne humeur ? Sans compter que plus tard dans la semaine, tu pourras participer à une chasse au trésor dans tout Toulouse - signée Hi7Haut - avec LE grand prix à remporter…
          <br>Dans la continuité du BDA actuel, nous poursuivrons lors du prochain mandat les incontournables tels que N7GT et le voyage à Barcelone. Les partenariats déjà mis en place seront conservés et nous en ajouterons des nouveaux (karaoké, cinéma et autres surprises !).
          <br>Mais ce n’est pas tout ! Nous proposerons de nouvelles activités culturelles aux élèves de l’n7, en faisant entrer par exemple le street art et l’art culinaire au BDA.

          Alors, qu’attends-tu pour t’initier à l’art de la piraterie ?</h3>
        <h3 v-else-if="isBDD(nom_bureau)">Qui a dit que la piraterie ne rimait pas avec écologie ?
          <br>Eh oui, nos pirates du BDD sont plus motivés que jamais pour contribuer à rendre la vie plus verte à l’école. Pendant les campagnes, nos matelots les plus responsables vous proposeront des activités diverses et variées.
          <br>Mais ce n’est pas tout ! Tout au long de l’année, le navire s’assurera de garder le cap vers un horizon plus vert. Pour cela, nous souhaitons organiser régulièrement des marches vertes ou encore des ateliers artisanaux. Nous souhaitons évidemment poursuivre le projet ecobox - les pirates en raffolent ! - et en commencer des nouveaux, comme la mise en place des lundis simples.
          <br>Chez Hi7Haut, matelots et corsaires vous donnent rendez-vous dans un monde plus vert !</h3>
        <h3 v-else-if="isFOY(nom_bureau)">Vous l'attendiez tous, voici l'équipage du Foy' !
          Maîtrisant l'art des chocos bien chaudes et des cafés allongés, nos pirates sauront vous réveiller entre 2 s̶i̶e̶s̶t̶e̶s CM, et étancher votre soif au cours de nombreux afterworks, concerts et soirées Foy' !
          <br>Et puisqu'un changement d'équipage est aussi l'occasion de remettre le bateau à neuf, nos pirates ont pour ambition de réaménager la cale du navire. Objectif: désengorger la salle chill pour valoriser ce lieu de détente et de convivialité.</h3>
      </div>
    </div>
    <membres-item v-bind:nom_bureau="nom_bureau"/>
  </div>
</template>

<script>
import MembresItem from "~/components/membres-item";
export default {
  name: "bureau-item",
  components: {MembresItem},
  props: ['nom_bureau'],
  methods: {
    isBDE(bureau) {
      return (bureau === "BDE")
    },
    isBDA(bureau) {
      return (bureau === "BDA")
    },
    isBDD(bureau) {
      return (bureau === "BDD")
    },
    isBDS(bureau) {
      return (bureau === "BDS")
    },
    isFOY(bureau) {
      return (bureau === "FOY")
    }

  }
}
</script>

<style lang="scss" scoped>
  #main_bureau {
    display: flex;
    flex-direction: column;
    .upper {
      display: flex;
      flex-direction: row;
      align-items: center;

      h1 {
        font-size: 80px;
        margin-right: 20px;
      }
      img {
        width: 100px;
        height: auto;
        margin: 0 20px;
      }
  }
    .lower {
      display: flex;
      flex-direction: row;
      justify-content: space-evenly;
      img {
        width: 200px;
      }
    }
  }

  @media screen and (max-width: 700px) {
    .upper {
      flex-direction: column !important;
      align-items: center;
    }
  }
</style>
