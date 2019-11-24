<template>
  <v-container fluid no-gutters class="px-0 py-0">
    <v-row class="px-0">
      <v-col cols="1">
        <v-icon color="black" v-if="filled">mdi-checkbox-blank-circle</v-icon>
        <v-icon color="black" v-else>mdi-checkbox-blank-circle-outline</v-icon>
      </v-col>
      <v-col cols="11" class="pl-4">
        {{ description }}
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'AssetEffect',
  props: [
    'filled',
    'description'
  ]
}
</script>
