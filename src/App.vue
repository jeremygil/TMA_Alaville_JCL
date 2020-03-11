<template>
  <v-app>
    <router-view></router-view>/>
  </v-app>
</template>

<script>


export default {
  name: "App",

  components: {  },

  data: () => ({})
};
</script>
<style lang="scss">
  @import "../node_modules/ag-grid-community/dist/styles/ag-grid.css";
  @import "../node_modules/ag-grid-community/dist/styles/ag-theme-balham.css";
</style>