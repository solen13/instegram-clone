<template>
 <div>

   <v-card flat width="100%" class="pa-4 d-flex justify-center">
    <input class="search"placeholder="Search..." type="text">
   </v-card>
 <div class="d-flex justify-center">
   <div style="width: 90%">
     <v-row>
       <v-col cols="4" v-for ="item in 40" :key="item">
         <v-img :src="`https://picsum.photos/2${item+20}`"></v-img>
       </v-col>
     </v-row>
   </div>
 </div>

 </div>
</template>

<script>
export default {
  name: "index"
}
</script>

<style scoped>
.search{
  background-color: rgba(128, 128, 128, 0.49);
  border-radius: 10px;
  width: 50%;
  height: 35px;
  outline: none;
  padding-left:30px ;
  color: white;
}
</style>
