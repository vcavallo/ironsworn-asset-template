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
      color="grey darken-2"
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
      color="grey darken-2"
      app
    >
    <v-row justify-space-between>
      <v-col class="text-right">
        <span class="white--text">
          Created by <a href="https://vinneycavallo.com">Vinney Cavallo</a> | <a href="https://github.com/vcavallo/ironsworn-asset-template">GitHub Repo</a>
        </span>
      </v-col>
    </v-row>
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
