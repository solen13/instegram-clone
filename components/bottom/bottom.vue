<template>
<div style="width: 100%;height: 72px"  class="white px-5">
  <div class="d-flex justify-center align-center mt-2 " style="gap:40px">

      <v-btn @click="$router.push('/')" icon>
        <v-img  max-width="24" height="24" src="/bottom/home.svg"></v-img>
      </v-btn>

      <v-btn @click="discover" icon>
        <v-img  max-width="24" height="24" src="/bottom/search.svg"></v-img>
      </v-btn>

      <v-btn icon>
        <v-img  max-width="24" height="24" src="/headerIcon/add.svg"></v-img>
      </v-btn>

      <v-btn @click="ses" icon>
        <v-img  max-width="24" height="24" src="/headerIcon/heart.svg"></v-img>
      </v-btn>

     <v-btn icon>
       <v-img class="rounded-circle" max-width="24" height="24" src="https://images.pexels.com/photos/733872/pexels-photo-733872.jpeg?auto=compress&cs=tinysrgb&w=600"></v-img>
     </v-btn>

  </div>
  <p class="text-center">--------</p>
</div>
</template>

<script>
export default {
  name: "bottom",
  methods:{
    discover(){
      this.$router.push('/discover')
    }
  }
}
</script>

<style scoped>

</style>
