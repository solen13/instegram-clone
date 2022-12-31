<template>
 <div v-if="getData" style="position: relative">

   <div  class="d-flex justify-space-between mb-2 white">

    <span>
      <v-btn @click="$router.push('/message')" icon>
        <v-icon>mdi-arrow-left</v-icon>
      </v-btn>
      <v-btn text >
         <v-img  class="rounded-circle " max-width="25" height="25" :src="getData.profileImage" ></v-img>
        {{getData.name}}
      </v-btn>

    </span>

     <span>
     <v-btn icon>
       <v-icon>mdi-phone</v-icon>
     </v-btn>

     <v-btn icon>
       <v-icon>mdi-video</v-icon>
     </v-btn>
    </span>
   </div>

   <div class="mb-16" style="height:520px; width: 100%; overflow-y: auto">
   <div class="message-contener" v-for="item in getData.message">

     <v-card flat style="margin-left: 50%" width="50%">
       <p class="ml-2 pa-2 rounded-xl grey lighten-3"> {{item.me}}</p>
     </v-card>

     <v-card flat width="50%" class="d-flex">
       <v-img  class="rounded-circle " max-width="20" height="20" :src="getData.profileImage" ></v-img>
       <p style="border: 1px solid black" class="ml-1 pa-2 rounded-xl"> {{item.its}}</p>
     </v-card>

   </div>

   </div>

   <div style="z-index: 99" class="sendMessage rounded-xl d-flex" >
     <v-btn icon>
       <v-icon>mdi-camera</v-icon>
     </v-btn>

     <input class="ml-1" style="width: 100%;outline: none" type="text" placeholder="text">

     <v-btn icon>
       <v-icon>mdi-microphone-settings</v-icon>
     </v-btn>

     <v-btn icon>
       <v-icon>mdi-image</v-icon>
     </v-btn>

   </div>

 </div>
</template>

<script>
import api from "../../constrant/messageApi";


export default {
  name: "message",
  data(){
    return{
      route:null
    }
  },
  mounted() {
   this.route= this.$route.params.message
  },
  computed:{
    getData(){
      if (this.route){
        return api[this.route]
      }
    }
  }
}
</script>

<style scoped>
.message-contener{
  width: 90%;

}
.sendMessage{
  position: fixed;
  bottom: 0;
  border: 1px solid grey;

  width: 100%;
  padding: 10px;
  overflow-y: auto;

}
@media only screen and (max-width:600px) {
  .sendMessage{
   margin-bottom: 80px;
  }
}
</style>
