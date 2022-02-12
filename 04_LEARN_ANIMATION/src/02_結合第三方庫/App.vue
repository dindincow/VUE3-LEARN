<template>
  <div class="box">
    <div><button @click="isShow=!isShow">隱藏/顯示</button></div>
 
    <transition name="din" >
      <h2 v-if="isShow">HOLLE WORLD</h2>
    </transition>
  </div>

</template>

<script>

export default{

  data(){
    return {
      isShow:true
    }
  }
}
</script>

<style lang="scss" scoped>

.din-enter-active{
   animation: swing 1s ease;
}
.din-leave-active{
  animation: swing 1s ease reverse;
}


</style>
