<template>
    <v-card @click="goPrfileDetail(data.name)" flat class="d-flex justify-space-between align-center px-3">
     <div class="profile">
      <v-img  class="rounded-circle" max-width="100%" height="100%" :src="data.profileImage" ></v-img>
     </div>
      <span class="ml-2" style="width: 100%">
        <h3>{{data.name}}</h3>
        <p>{{data.lastMessage}} -{{data.date}}</p>
      </span>

      <v-btn icon> <v-icon>mdi-camera</v-icon> </v-btn>
    </v-card>
</template>

<script>
export default {
  name: "message",
  props:{
    data:{
      type:Object,
      default:()=>{}
    }
  },
  methods:{
    goPrfileDetail(item){

      this.$router.push('/message/'+item)
    }
  }
}
</script>

<style scoped>
.profile{
  width: 60px;
  height: 60px;
}
</style>
