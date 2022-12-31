<template>
   <div>
     <message-nav-bar  class="message" :data="getData" />
     <div class="d-flex justify-center mt-4" v-for="item in getData">
       <message class="message" :data="item" />
     </div>
   </div>
</template>

<script>

import Message from "../../components/message/message";
import api from '../../constrant/messageApi'
import MessageNavBar from "../../components/nav-bar/messageNavBar";
export default {
  name: "index",
  components: {MessageNavBar, Message},
  computed:{
    getData(){
      return api
    }
  }
}
</script>

<style scoped>
.message{
  width: 350px;
}
</style>
