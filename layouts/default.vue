<template>
  <v-app style="position: relative">
    <nav-bar style="position: fixed ; z-index: 99" />
    <Nuxt/>
    <bottom class="hidden-sm-and-up" style="position: fixed ; bottom: 0 ;z-index: 99"/>
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
