<template>
  <router-view></router-view>
</template>

<script>
import {onMounted} from 'vue'
export default {
  name: 'App',
  setup(){

  }

}
</script>

<style>

*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
*:focus{
  outline: none;
}

body,html{
  font-family: 'open';
  color:var(--body-text-color);
  font-weight: 400;
  font-size: 1rem;
  overflow-x: hidden;
}
p.text{
  font-weight: bold;
}
.title{
  font-family: 'rail';
}
</style>
