<template>
  <div v-if="data">
     <div  style="width: 300px;height: 100vh;"  class="red story-content">
cscsc
     </div>
  </div>
</template>

<script>
export default {
  name: "fullStoryShow",
  props:{
    data:{
      type:Object,
      default:()=>{}
    }
  }
}
</script>

<style scoped>
.story-content{
}
</style>
