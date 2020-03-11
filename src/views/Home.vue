<template>
  <v-app id="inspire">
    <v-content>
      <v-container>
        <v-select
          v-model="Magasin"
          :items="LesMagasins"
          item-text="libelle"
          item-value="libelle"
          label="Choix magasin"
          outlined
          dense
          return-object="Magasin"
        ></v-select>
        <v-select
          v-model="Produit"
          :items="LesProduits"
          item-text="libelle"
          item-value="libelle"
          label="Choix produit"
          dense
          outlined
          return-object="Produit"
        ></v-select>
        <v-select
          v-model="Acheteur"
          :items="LesAcheteurs"
          item-text="nom"
          item-value="nom"
          label="Choix acheteur"
          outlined
          return-object="Acheteur"
          dense
        ></v-select>
        <v-btn
          class="ma-2"
          :loading="loading"
          :disabled="loading"
          color="secondary"
          @click="loader = 'loading', alertMessage()"
        >Ajouter Panier</v-btn>
      </v-container>
      <p v-if="ajoutPanier">{{MessageAjoutPanier}}</p>
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
    loader: null,
    loading: false,
    ajoutPanier: false,
    MessageAjoutPanier: "",
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
  methods: {
    alertMessage() {
      this.ajoutPanier = true;
      this.MessageAjoutPanier =
        "Bonjour Monsieur " +
        this.Acheteur.nom +
        " " +
        this.Acheteur.prenom +
        ", vous avez acheter sur le magasin de " +
        this.Magasin.libelle +
        ", le produit " +
        this.Produit.libelle +
        " à " +
        this.Produit.prix +
        "€";
    }
  },
  watch: {
    loader() {
      const l = this.loader;
      this[l] = !this[l];

      setTimeout(() => (this[l] = false), 3000);

      this.loader = null;
    }
  }
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
.custom-loader {
  animation: loader 1s infinite;
  display: flex;
}
@-moz-keyframes loader {
  from {
    transform: rotate(0);
  }
  to {
    transform: rotate(360deg);
  }
}
@-webkit-keyframes loader {
  from {
    transform: rotate(0);
  }
  to {
    transform: rotate(360deg);
  }
}
@-o-keyframes loader {
  from {
    transform: rotate(0);
  }
  to {
    transform: rotate(360deg);
  }
}
@keyframes loader {
  from {
    transform: rotate(0);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>