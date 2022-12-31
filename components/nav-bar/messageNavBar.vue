<template>
  <div class="d-flex justify-space-between">

    <span>
      <v-btn @click="$router.push('/')" icon>
        <v-icon>mdi-arrow-left</v-icon>
      </v-btn>
      <v-btn text>
        john<v-icon>mdi-chevron-down</v-icon>
      </v-btn>

    </span>

    <span>
     <v-btn icon>
       <v-icon>mdi-video</v-icon>
     </v-btn>

     <v-btn icon>
       <v-icon>mdi-plus</v-icon>
     </v-btn>
    </span>
  </div>
</template>

<script>
export default {
  name: "messageNavBar",
  props:{
    data:{
      type:String,
      default:''
    }
  }
}
</script>

<style scoped>

</style>
