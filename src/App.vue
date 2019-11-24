<template>
  <v-app id="ironsworn-asset-template">
    <v-navigation-drawer
      stateless
      v-model="drawer"
      app
    >
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-home</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Asset Generator</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="indigo"
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Ironsworn Asset Template</v-toolbar-title>
    </v-app-bar>

    <v-content>
      <v-container
        class="fill-height"
        fluid
      >
        <AssetGenContainer />
      </v-container>
    </v-content>

    <v-footer
      color="indigo"
      app
    >
      <span class="white--text">&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
import AssetGenContainer from './components/AssetGenContainer.vue'

export default {
  name: 'App',
  components: {
    AssetGenContainer,
  },
  props: {
  },
  data: () => ({
    drawer: false,
  }),
};
</script>
