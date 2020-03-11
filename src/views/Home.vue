<template>
  <v-app id="inspire">
    <v-content>
      <v-container>
        <v-select
          v-model="Magasin"
          :items="LesMagasins"
          item-text="libelle"
          item-value="numero"
          label="Choix magasin"
          outlined
          dense
        ></v-select>
        <v-select
          v-model="Produit"
          :items="LesProduits"
          item-text="libelle"
          item-value="id"
          label="Choix produit"
          dense
          outlined
        ></v-select>
        <v-select
          v-model="Acheteur"
          :items="LesAcheteurs"
          item-text="nom"
          item-value="id"
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
        prix: "2"
      },
      {
        id: 4,
        libelle: "Pepsi",
        prix: "1.4"
      },
      {
        id: 5,
        libelle: "Tomate",
        prix: "1.5"
      },
      {
        id: 6,
        libelle: "Brocolis",
        prix: "0.8"
      },
      {
        id: 7,
        libelle: "Chocolat",
        prix: "1.8"
      },
      {
        id: 8,
        libelle: "Fraise",
        prix: "1.1"
      },
      {
        id: 9,
        libelle: "Chou",
        prix: "1.0"
      },
      {
        id: 10,
        libelle: "Carotte",
        prix: "0.9"
      }
    ],
    LesAcheteurs: [
      {
        id: 1,
        nom: "robert",
        prenom: "vincent"
      },
      {
        id: 2,
        nom: "Jorge",
        prenom: "Marc"
      },
      {
        id: 3,
        nom: "Luc",
        prenom: "Thomas"
      },
      {
        id: 4,
        nom: "Harris",
        prenom: "vincent"
      },
      {
        id: 5,
        nom: "John",
        prenom: "Michael"
      }
    ]
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