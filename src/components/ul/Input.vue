<template>
  <div class="flowInput">
    <p @click="focusIn" :class="{goTop:isFocus}" ref="p">{{label}}</p>
    <input v-if="element==='input'" ref="input" @focus="focusIn" @focusout="onfocus" type="text">
    <textarea v-else-if="element==='textArea'" ref="input" @focus="focusIn" @focusout="onfocus"></textarea>
  </div>
</template>

<script>
import {ref} from 'vue'
export default {
  setup(){
    const input=ref(null)
    const p=ref(null)
    const isFocus=ref(null)
    function onfocus(){
      if(input.value.value.trim().length===0){
        isFocus.value=false

      }
    }
    function focusIn(){
      isFocus.value=true
      input.value.focus()

    }
    return{
      onfocus,
      focusIn,
      p,
      input,
      isFocus
    }
  },
  name: "Input",
  props:['label','type','element']
}
</script>

<style scoped>
.flowInput{
  position: relative;
  padding: 10px;
  width: 100%;
}
input{
  padding: 20px 15px;
  border: 1px solid #ced4da;
  width: 100%;
  font-size: 14px;
}
p{
  z-index: 2;
  position: absolute;
  left: 20px;
  user-select: none;
  top: 35px;
  transition: all 0.3s linear;
  transform: translateY(-50%);
}
.goTop{
  font-size: 14px;
  color: var(--logo-red);
  font-weight: bold;
  top: 20px;

}
textarea{
  width: 100%;
  height: 150px;
  border: 1px solid #ced4da;
  padding: 20px 15px;
  resize: vertical;
}
</style>