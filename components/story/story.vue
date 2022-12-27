<template>
  <v-card  flat max-width="100%" height="95"  >

      <v-card flat style="position: relative" max-width="72" height="95">

        <div  class="story  rounded-circle" >

          <div  class="rounded-circle" style="border: 3px solid white ; width: 95%;height: 95%;position: relative " >
            <v-img  class="rounded-circle" max-width="100%" height="100%" :src="data.image"></v-img>
            <v-btn v-if="data.me" icon small style="position: absolute;right: 0" fab>
              <v-icon class="blue white--text rounded-circle mb-10" >{{ data.me }}</v-icon>
            </v-btn>
          </div>

        </div>

        <div style="width: 100%">
          <p  class="text-center caption">{{data.name}}</p>
        </div>
      </v-card>


  </v-card>
</template>

<script>
export default {
  name: "story",
  props:{
    data:{
      type:Object,
      default:()=>{}
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
  background-image: linear-gradient(to right top, #ffdd55, #ffb74b, #ff8f56, #ff686c, #fe4687, #f63c8b, #ed338f, #e42a93, #f2297f, #fc3269, #ff4254, #ff543e);
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));

}
.name{
  position: absolute;
  bottom: 0;
  width: 72px;
  height: 8px;

}
</style>
