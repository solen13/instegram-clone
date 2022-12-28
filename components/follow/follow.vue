<template>

  <div   class="follow pa-3" style="overflow-x: auto;gap: 10px ;width: 100%" >

    <v-card class="pa-2" width="250" height="254" v-for="item in data" style="position: relative">
      <v-btn @click="exitBtn(item)" class="exit" icon>
        <v-icon>mdi-close</v-icon>
      </v-btn>
      <div >
        <v-img class="rounded-circle" max-width="140" height="140"  :src="item.imageUrl"></v-img>
        <h2  style="font-size: 16px" class="font-weight-medium text-center black--text mt-1" >{{item.name}}</h2>
        <h5 class="text-center grey--text">Popular</h5>
      </div>
      <v-btn v-if="remove" height="23" width="100%" text class="blue white--text mt-6">follow</v-btn>
    </v-card>

  </div>

</template>

<script>
export default {
  name: "follow",
  data(){
    return{
      remove:true
    }
  },
  props:{
    data:{
      type:Array,
      default:[]
    }
  },
  methods:{
    exitBtn(item){
      alert()
      console.log(item)
      this.remove=false
    }
  }
}
</script>

<style scoped>
.exit{
  position: absolute;
  right: 0;
  top: 0;
  z-index: 97;
}
.follow{
 display: flex;

}
</style>
