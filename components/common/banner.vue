<template>
  <div class="mt-3">

    <div v-if="data.profileImage"  style="height:72px ;border-bottom:.5px solid gray" class="d-flex justify-space-between align-center px-2">
      <span  @click="goProfile(data)" class="d-flex" style="width: 100%" >
        <div  class="story  rounded-circle" >
          <div  class="rounded-circle" style="border: 3px solid white ; width: 95%;height: 95%" >
            <v-img  class="rounded-circle" max-width="100%" height="100%" :src="data.profileImage" ></v-img>
          </div>
        </div>
        <h2  class="title ml-2">{{ data.name }}</h2>
      </span>

      <v-btn   @click="sheet = !sheet" icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>


    </div>


   <v-img class="mt-1" v-on:dblclick="isLike = ! isLike" v-if="data.profileImage" max-width="100%"  height="460" :src="data.postImage"></v-img>
    <div v-if="data.profileImage" style="width: 100% " class="d-flex justify-space-between px-2 mt-1">
      <div class="d-flex" style="gap:10px" >

        <v-btn @click="isLike = ! isLike" icon>
          <v-img  v-if="isLike"  max-width="24" height="24" src="/headerIcon/isHeart.svg"></v-img>
          <v-img  v-else max-width="24" height="24" src="/headerIcon/heart.svg"></v-img>

        </v-btn>

        <v-btn icon>
          <v-img  max-width="24" height="24" src="/headerIcon/comment.svg"></v-img>
        </v-btn>

        <v-btn icon>
          <v-img  max-width="24" height="24" src="/headerIcon/message.svg"></v-img>
        </v-btn>

      </div>


      <div >
        <v-btn @click="datas()" tyle="z-index: 97" icon  >
          <v-img   v-if="datalar" max-width="24" height="24" src="/headerIcon/isSave.svg"></v-img>
          <v-img  v-else max-width="24" height="24" src="/headerIcon/save.svg"></v-img>
        </v-btn>

      </div>

    </div>



    <div  v-if="data.profileImage" class="px-3 mt-2">
        <h5>23,034 likes</h5>

        <span  style="height:48px;width: 100%" >
           <span class="d-flex">
             <h3  >{{ data.name }}</h3>
             <p class="ml-2">Lorem ipsum dolor sit amet amet.</p>
           </span>
          <p class="grey--text">view all {{data.numberComment }} Comment </p>
       </span>
        <div class="profie">
          <v-btn icon>
            <v-img class="rounded-circle" max-width="34" height="34" :src="data.profileImage"></v-img>
          </v-btn>
          <input class="ml-1" type="text" placeholder="Add a comment..">
        </div>

      <p class="mt-1 grey--text">{{ data.date }}</p>

    </div>

    <div class="hidden-md-and-up" v-if="data.show" >
       <follow :data="data.sorce"/>
    </div>

    <div >
      <v-bottom-sheet v-model="sheet" inset>

        <v-sheet
          class="text-center"
          height="400px"
          style="border-top-left-radius:30px ; border-top-right-radius: 30px "
        >

          <div class="my-3">

          <div class="pa-4">

            <v-btn elevation="0"  fab style="border: 2px solid black" >
              <v-icon>mdi-share-variant-outline</v-icon>
            </v-btn>

            <v-btn  elevation="0"  fab style="border: 2px solid black">
              <v-icon>mdi-connection</v-icon>
            </v-btn>

            <v-btn  elevation="0"  fab style="border: 2px solid black" >
              <v-icon>mdi-repeat</v-icon>
            </v-btn>

            <v-btn  elevation="0"  fab style="border: 2px solid black">
              <v-img  max-width="24" height="24" src="/headerIcon/save.svg"></v-img>
            </v-btn>

            <v-btn  elevation="0"  fab style="border: 2px solid black">
              <v-icon>mdi-qrcode-scan</v-icon>
            </v-btn>
          </div>

            <hr>
         <div class="menu-detail">
           <span class="pa-3">
             <v-icon class="mr-1">mdi-hexagram-outline</v-icon> fovoriler ekle
           </span>
           <span class="pa-3">
             <v-icon class="mr-1">mdi-account-minus-outline</v-icon> takibi bırak
           </span>
         </div>
            <hr>

           <div class="menu-detail">
             <span class="pa-3">
             <v-icon class="mr-1">mdi-alert-circle-outline</v-icon> Bu gonderi neden gormuyom
           </span>

             <span class="pa-3">
                 <v-icon class="mr-1">mdi-eye-off</v-icon> Gizle
           </span>
             <span class="pa-3 red--text">
              <v-icon class="red--text mr-1">mdi-comment-alert-outline</v-icon> şikayet et
           </span>
           </div>


          </div>
        </v-sheet>
      </v-bottom-sheet>
    </div>
  </div>
</template>

<script>

import Follow from "~/components/follow/follow";
export default {
  name: "banner",
  components: {Follow},
  data(){
    return{
    datalar:false,
      isLike:false,
      sheet: false,
    }
  },
  props:{
    data:{
      type:Object,
      default:()=>{}
    }
  },
  methods:{
    goProfile(item){
      console.log(item.name)
      this.$router.push('/profile/'+item.name)
    },

    datas(){
     this.datalar = ! this.datalar
    }

  },

  computed:{
    datam(){
      return this.data.isSave
    }
  }

}
</script>

<style scoped>
.story{
  width: 38px;
  height: 38px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: linear-gradient(to right top, #ffdd55, #ffb74b, #ff8f56, #ff686c, #fe4687, #f63c8b, #ed338f, #e42a93, #f2297f, #fc3269, #ff4254, #ff543e);
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));

}
.icon{
  font-size: 35px;
}
.menu-detail{
  display: flex;
  flex-flow: column;
  justify-content: flex-start;
  align-items: flex-start;
}
</style>
