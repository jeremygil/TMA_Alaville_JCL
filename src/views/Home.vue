<template>
  <v-app id="inspire">
    <v-content>
      <v-container></v-container>
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
  data: () => ({}),
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