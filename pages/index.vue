<template>
  <v-main class="mt-16 mb-16">

    <div  style="width: 100%; height: 95px;overflow-x: auto;overflow-y:hidden;  gap:10px" class="d-flex banner">
      <div  v-for="item in storyApi">
        <story  :data="item" />
      </div>
    </div>


    <div v-for="(item,index) in getApi" :key="index">
      <banner :data="item" class="banner"/>
    </div>
    <follow/>

  </v-main>
</template>

<script>
import Story from "../components/story/story";
import Banner from "../components/common/banner";
import Follow from "../components/follow/follow";
import getApi from '../constrant/api'
import storyApi from '../constrant/storyApi'
export default {
  name: 'IndexPage',
  components: {Follow, Banner, Story},
  computed:{
    getApi(){
      return getApi
    },
    storyApi(){
      return storyApi
    }
  }
}
</script>
<style>
@media only screen and (min-width:600px) {
  .banner{
    width: 600px;
  }
}
@media only screen and (max-width:600px) {
  .banner{
    width: 100%;
  }
}
</style>
