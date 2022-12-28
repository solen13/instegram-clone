<template>
  <div v-if="getData" class="mt-16">

    <div  class="d-flex justify-center" >

     <span>
      <v-img  class="rounded-circle" max-width="100" height="100" :src="getData.profileImage" ></v-img>
       <div>
          <h3 class="text-center mt-1">{{getData.name}}</h3>
           <span v-for="item in getData.profile.bio">
            <span v-html="item"></span>
           </span>
       </div>
     </span>

     <div class="ml-2">
      <span class="d-flex  mt-2" >

         <div class="px-2">
           <h4 class="text-center">{{getData.profile.profiles.post}}</h4>
            <p class="text-end">Post</p>
         </div>

         <div class="px-2">
           <h4 class="text-center">{{getData.profile.profiles.followers}}</h4>
            <p class="text-end">followers</p>
         </div>


         <div class="px-2">
           <h4 class="text-center">{{getData.profile.profiles.following}}</h4>
            <p class="text-end">following</p>
         </div>

      </span>
      <v-btn style=" height: 30px" class="blue white--text">Follow</v-btn>
      <v-btn style=" height: 30px" class="grey white--text">message</v-btn>
    </div>

  </div>

    <div class="story-contener ">
      <v-sheet  width="100%" >
        <v-slide-group class="pa-3">
          <v-slide-item v-for="(item,index) in getData.profile.story" :key="index" class="pa-2">
            <v-card flat style="position: relative" max-width="82" height="95" >
              <div  class="story  rounded-circle" >
                <div  class="rounded-circle" style="border: 3px solid white ; width: 95%;height: 95%;position: relative " >
                  <v-img  class="rounded-circle" max-width="100%" height="100%" :src="item.imageUrl"></v-img>
                </div>
              </div>
              <div style="width: 100%">
                <p  class="text-center caption">{{item.name}}</p>
              </div>
            </v-card>
          </v-slide-item>
        </v-slide-group>
      </v-sheet>
    </div>

    <div class="mb-16 all-image"  >
      <div class="img-contener">
        <v-row style="width: 100%">
          <v-col cols="4"  lg="3" v-for="(item,index) in getData.profile.allPost" :key="index">
            <v-img max-width="100" height="100" :src="item.imageUrl"></v-img>
          </v-col>
        </v-row>
      </div>
    </div>

  </div>
</template>

<script>
import api from '../../constrant/api'
export default {
  name: "index",
  data(){
    return{
    route:null
    }
  },
  mounted() {
    this.route=this.$route.params.person
  },
  computed:{
    getData(){
      if(this.route){
        return api[this.route]
      }
    }
  }
}
</script>

<style scoped>
.story{
  width: 72px;
  height: 72px;
  display: flex;
  justify-content: center;
  align-items: center;
  background:grey;
}
.all-image{
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

}

@media only screen and (min-width:600px) {
  .img-contener{
  width:50%;
  }
  .story-contener{
    width: 50%;
   margin-left: auto;
   margin-right: auto;
  }
}
@media only screen and (max-width:600px) {
  .img-contener{
    width:90%;

    display: flex;
    justify-content: center;
  }
  .story-contener{
    width: 97%;

  }
}
</style>
