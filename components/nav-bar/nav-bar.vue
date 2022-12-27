<template>
 <div class="white d-flex align-center"  style="width: 100% ;height: 56px" >

   <div  style="width: 100% " class="d-flex px-3 justify-space-between align-center ">
     <div>
       <v-img max-width="122" height="40" src="/headerIcon/Instagram_logo.svg"></v-img>
     </div>

     <input class="hidden-sm-and-down" type="text" placeholder="search">
     <div class="d-flex" style="gap:20px ">

       <v-btn class="hidden-sm-and-down" icon>
         <v-img  max-width="24" height="24" src="/bottom/home.svg"></v-img>
       </v-btn>

        <v-btn icon>
          <v-img  max-width="24" height="24" src="/headerIcon/add.svg"></v-img>
        </v-btn>

       <v-btn icon>
         <v-img  max-width="24" height="24" src="/headerIcon/heart.svg"></v-img>
       </v-btn>

       <v-btn class="hidden-sm-and-down" icon>
         <v-img  max-width="24" height="24" src="/headerIcon/menus.svg"></v-img>
       </v-btn>

        <v-btn icon>
          <v-img  max-width="24" height="24" src="/headerIcon/message.svg"></v-img>
        </v-btn>

       <v-btn class="hidden-sm-and-down" icon>
         <v-img class="rounded-circle" max-width="24" height="24" src="https://images.pexels.com/photos/733872/pexels-photo-733872.jpeg?auto=compress&cs=tinysrgb&w=600"></v-img>
       </v-btn>

     </div>
   </div>

 </div>

</template>

<script>
export default {
  name: "nav-bar"
}
</script>

<style scoped>

</style>
