<template>
  <v-app id="inspire">
    <v-content>
      <v-container>
        <v-select
          v-model="Magasin"
          :items="LesMagasins"
          item-text="libelle"
          label="Choix magasin"
          outlined
          dense
        ></v-select>
        <v-select
          v-model="Produit"
          :items="LesProduits"
          item-text="libelle"
          label="Choix produit"
          dense
          outlined
        ></v-select>
        <v-select
          v-model="Acheteur"
          :items="LesAcheteurs"
          item-text="libelle"
          label="Choix acheteur"
          outlined
          dense
        ></v-select>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  props: {
    source: String
  },
  components: {},
  beforeMount() {},
  data: () => ({
    Magasin: null,
    Produit: null,
    Acheteur: null,
    LesMagasins: [
      {
        numero: 1,
        libelle: "Roncq"
      },
      {
        numero: 2,
        libelle: "Tourcoing"
      },
      {
        numero: 3,
        libelle: "Lille"
      },
      {
        numero: 4,
        libelle: "Villeneuve D'ascq"
      },
      {
        numero: 5,
        libelle: "Mouscron"
      }
    ],
    LesProduits: [
      {
        id: 1,
        libelle: "Yaourt",
        prix: "1"
      },
      {
        id: 2,
        libelle: "Coca-Cola",
        prix: "1.5"
      },
      {
        id: 3,
        libelle: "Sandwich",
        prix: "2.5"
      },
      {
        id: 4,
        libelle: "Pepsi",
        prix: "1.5"
      }
    ],
    LesAcheteurs: []
  }),
  created() {
    this.$vuetify.theme.light = true;
  },
  computed: {
    headersContraintes: function() {
      return "";
    }
  },
  mounted() {},
  methods: {}
};
</script>

<style media="only screen">
html,
body {
  height: 100%;
  width: 100%;
  margin: 0;
  box-sizing: border-box;
  -webkit-overflow-scrolling: touch;
}
html {
  position: absolute;
  top: 0;
  left: 0;
  padding: 0;
  overflow: auto;
}
body {
  padding: 1rem;
  overflow: auto;
}
</style>