<template>
  <v-app style="position: relative">
    <Nuxt/>
    <bottom class="hidden-sm-and-up" style="position: fixed ; bottom: 0 ;z-index: 98"/>
  </v-app>
</template>

<script>
import NavBar from "../components/nav-bar/nav-bar";
import Bottom from "../components/bottom/bottom";
import DestopFollow from "../components/follow/destopFollow";
export default {
  name: 'DefaultLayout',
  components: {DestopFollow, Bottom, NavBar},
}
</script>
