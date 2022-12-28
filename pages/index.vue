<template>
  <v-main class="mt-16 mb-16" >
<div class="contaniers"  style="position: relative">

  <div>
    <div class=" story blue">
        <story  :data="storyApi" />
    </div>

    <div v-for="(item,index) in getApi" :key="index">
      <banner :data="item" class="banner"/>
    </div>

  </div>
  <div class="destopFollow" style="position: fixed;right: 0" >
    <destop-follow/>
  </div>


</div>
  </v-main>
</template>

<script>
import Story from "../components/story/story";
import Banner from "../components/common/banner";
import getApi from '../constrant/api'
import storyApi from '../constrant/storyApi'
import DestopFollow from "../components/follow/destopFollow";
export default {
  name: 'IndexPage',
  components: {DestopFollow, Banner, Story},
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
@media only screen and (max-width:800px) {

  .destopFollow{
    display: none;
  }
}
@media only screen and (min-width:600px) {
  .banner{
    width: 850px;
  }
  .contaniers{
    display: flex;
  }
  .story{
    width: 850px;
  }
  .destopFollow{
    width: 20%;
    margin-right: 130px;
  }
}
@media only screen and (max-width:600px) {
  .banner{
    width: 100%;
  }
  .destopFollow{
    display: none;
  }
  .story{
    width: 90%;
  }

}
</style>
