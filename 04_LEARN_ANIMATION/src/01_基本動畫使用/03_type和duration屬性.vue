<template>
  <div class="box">
    <div><button @click="isShow=!isShow">隱藏/顯示</button></div>
    <!-- type: transition/animation 看要以哪個當動畫時間結束點-->
    <transition name="din" type="transition" :duration="8000">
      <div v-if="isShow" class="title">HOLLE WORLD</div>
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
.box{
  width: 200px;
  margin: 50px auto;
}
.title{
  margin-top: 30px;
}

.din-enter-from,
.din-leave-to{
  opacity: 0;
}

.din-enter-active,
.din-leave-active{
  transition: opacity 1s ease;
}


.din-enter-active{
  animation:bounce 1s ease;
}
.din-leave-active{
  animation:bounce 1s ease reverse;
}

@keyframes bounce {
  0%{
    transform: scale(0);
  }
  50%{
    transform: scale(1.2);
  }
  100%{
    transform: scale(1);
  }
}
</style>
