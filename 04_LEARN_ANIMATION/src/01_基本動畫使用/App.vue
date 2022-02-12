<template>
  <div class="box">
    <div><button @click="isShow=!isShow">隱藏/顯示</button></div>
    <!--- mode:out-in 先出去在近來 , appear 一近來就有動畫效果--->
    <transition name="din" mode="out-in" appear>
      <component :is="isShow?'Home':'About'"></component>
    </transition>
  </div>

</template>

<script>
import Home from './pages/Home.vue'
import About from './pages/About.vue'
export default{
  components:{Home,About},
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
