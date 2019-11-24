<template>
  <div>
    <v-icon v-if="filled">mdi-checkbox-blank-circle</v-icon>
    <v-icon v-else>mdi-checkbox-blank-circle-outline</v-icon>
    {{ description }}
  </div>
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
