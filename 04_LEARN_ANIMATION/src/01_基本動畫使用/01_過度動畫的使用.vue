<template>
  <button @click="isShow=!isShow">隱藏/顯示</button>
  <transition name="din">
      <div v-if="isShow">HOLLE WORLD</div>
  </transition>

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
.din-enter-from,
.din-leave-to{
  opacity: 0;
}

.din-enter-to,
.din-leave-from{
  opacity: 1;
}

.din-enter-active,
.din-leave-active{
  transition: 1s ease-in;
}

</style>
