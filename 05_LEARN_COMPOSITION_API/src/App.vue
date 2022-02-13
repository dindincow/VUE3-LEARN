<template>
  <div>
    <div>{{info.name}}</div>
    <div>{{info.age}}</div>
    <div>{{info.hobby}}</div>
    <div>{{info.other.a.b.c}}</div>
    <button @click="changeInfo">改變資訊</button>
  </div>
  
</template>

<script>
import {reactive} from 'vue'

export default {
  name: 'App',
  setup(){
    let info = reactive({
      name:'jessica',
      age:18,
      hobby:['sleep','drink'],
      other:{
        a:{
          b:{
            c:'qoo good'
          }
        }
      }
    })
    const  changeInfo = ()=>{
      info.name = "qoo";
      info.age = 55;
      info.hobby[0] = 'palygame';
      info.other.a.b.c ="666"
    }
    return{
      changeInfo,
      info
    }
  }
}
</script>

