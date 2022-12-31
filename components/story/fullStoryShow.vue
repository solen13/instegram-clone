<template>
  <div v-if="data">

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
