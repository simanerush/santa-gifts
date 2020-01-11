<template>
  <v-app>
    <v-content>
      <v-app-bar
        color="red lighten-1"
        dark
      >
      <v-toolbar-title>Служба доставки подарков</v-toolbar-title>
      </v-app-bar>
      
     <info class ="mt-10"></info>
    </v-content>
</v-app>
</template>

<script>
import info from './components/info.vue'


export default {
  name: 'App',

  components: {
    info,
  },
}
</script>

<style>

</style>