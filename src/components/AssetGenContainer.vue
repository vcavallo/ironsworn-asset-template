<template>
  <v-container
    style="height: 100%;"
  >
    <v-row justify-space-between>
      <v-col class="order-xs-1 order-md-12 col-12 col-md-6">
        <v-row justify-content-end>
          <v-spacer />
          <v-col cols="3">
            <v-btn icon disabled><v-icon>mdi-printer</v-icon></v-btn>
            <v-btn icon disabled><v-icon>mdi-image</v-icon></v-btn>
          </v-col>
        </v-row>

        <v-row>
          <v-spacer />
          <v-col cols="10">
            <v-container fluid no-gutters class="asset-card py-0">
              <v-row class="pl-0">
                <v-col class="pt-3 pb-0 pl-2 black white--text">
                  <h2>{{ assetType }}</h2>
                </v-col>
              </v-row>

              <v-row class="pl-2 pt-2">
                <h1>{{ title }}</h1>
              </v-row>

              <v-row class="pl-2 pb-0">
                <p class="mb-0">{{ description }}</p>
              </v-row>

              <v-row v-for="effect in effects" :key="effect.id" class="pl-2 pt-0">
                <AssetEffect :filled='effect.filled' :description="effect.description" />
              </v-row>
            </v-container>
          </v-col>
        </v-row>

      </v-col>

      <v-col class="order-xs-12 order-md-1 col-12 col-md-6 fixed-form pa-4">
        <v-row>
          <v-text-field
            v-model="assetType"
            label="Asset Type"
          />
        </v-row>
        <v-row>
          <v-text-field
            v-model="title"
            label="Title"
          />
        </v-row>
        <v-row>
          <v-textarea
            v-model="description"
            label="Description"
          />
        </v-row>

        <v-row v-for="effect in effects" :key="effect.id">
          <v-switch
            v-model="effect.filled"
            class="mr-2"
          />
          <v-textarea
            v-model="effect.description"
            label="Effect Description"
          />
        </v-row>

        <v-row>
          <v-btn @click="addEffect">Add Effect</v-btn>
        </v-row>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>

import AssetEffect from './AssetEffect.vue'

export default {

  props: {
  },

  components: {
    AssetEffect,
  },

  created () {
  },

  data: () => {
    return {
      effectId: 1,
      assetType: 'Path',
      title: 'Title Here',
      description: 'Optional description text that appears above the mechanics',
      effects: [],
      newEffectFilled: false,
      newEffectDescription: 'This is an effect of this asset. It can be filled or left empty',
    }
  },

  methods: {
    findEffectById(id) {
      return this.effects.find(e => e.id == id)
    },

    addEffect () {
      let effect = {
        id: this.effectId,
        filled: false,
        description: ''
      }
      this.effects.push(effect)
      this.effectId++
    }

  },

};

</script>

<style scoped>

.asset-card {
  border-radius: 5px;
  border: 2px solid black;
  min-height: 440px;
  width: 300px;
}

.fixed-form {
  /*
  max-height: 70vh;
  overflow-y: scroll;
  */
}

body {
  font-family: Georgia, "Palatino Linotype", "Book Antiqua", Palatino, serif;
}

.header {
  font-weight: bolder;
  text-transform: uppercase;
  color: white;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

</style>
