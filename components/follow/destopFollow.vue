<template>

    <div class="follow">
     <div class="d-flex justify-space-between">

       <span class="d-flex">
         <v-img class="rounded-circle" max-width="56" height="56"  src="https://images.pexels.com/photos/1090387/pexels-photo-1090387.jpeg?auto=compress&cs=tinysrgb&w=600"></v-img>

         <span class="ml-3">
           <h2 class="subtitle-2">Sinem</h2>
           <h4 class="subtitle-2 grey--text">Sinemj</h4>
         </span>

       </span>
       <v-btn text class="blue--text">Switch</v-btn>

     </div>



      <div class="mt-5">

        <div class="d-flex justify-space-between ">
          <p class="grey--text">Suggestions For You</p>
          <v-btn text>See All</v-btn>
        </div>

        <div class="d-flex justify-space-between" v-for="item in 5">
         <span class="d-flex ">
           <v-img class="rounded-circle mt-2" max-width="32" height="32"  src="https://images.pexels.com/photos/1090387/pexels-photo-1090387.jpeg?auto=compress&cs=tinysrgb&w=600"></v-img>
           <span class="ml-2">
             <h2 class="subtitle-1">tekjfb</h2>
             <p class="caption mt-1 grey--text">Followed by terylucas</p>
           </span>
         </span>
          <v-btn text class="blue--text"> Follow</v-btn>
        </div>

      </div>

    </div>

</template>

<script>
export default {
  name: "destopFollow",
  components: {}

}
</script>

<style scoped>
.follow{
  width: 100%;
  height: 100vh;
}
</style>
