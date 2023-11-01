<script setup>
import { ref } from 'vue';

let qty = ref(0)

function addValue(){
  if(qty.value>=99){
    qty.value="+99"
  }else{
    qty.value++
  }
}
function minusValue(){
  if(qty.value>0){
    qty.value--
  }
}
</script>

<template>
 <div class="wrapper">
  <div class="profile">
    <div class="ballon" v-if="qty>0">{{ qty }}</div>
  </div>
  <div class="buttom-wrapper">
    <div class="buttom" @click="addValue">+</div>
    <div class="buttom" @click="minusValue">-</div>
  </div>
  <div class="notification" v-if="qty>0">(⌐■_■)</div>
  <div class="notification" v-if="qty==0">(╯°□°）╯︵ ┻━┻</div>
 </div>
</template>

<style scoped>
.notification{
  text-align: center;
}
.buttom{
  width: 32px;
  background-color: #F2CB05;
  display: inline-block;
  padding: 4px 0;
  border-radius: 4px;
  margin: 0 8px;
}
.buttom:hover{
cursor: pointer;
background-color: #F23030;
}
.buttom-wrapper{
margin-top: 16px;
margin-bottom: 16px;
text-align: center;
}
.ballon{
  position: absolute;
  top: 0px;
  right: 0px;
  width: 32px;
  height: 32px;
  background-color: #F28705;
  border-radius: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
.profile{
  background-image: url(https://pbs.twimg.com/profile_images/520777752983519232/SD31s4zo_400x400.jpeg) ;
  background-size: cover;
  position: relative;
  background-color: orange;
  width: 120px;
  height: 120PX;
  margin: 0 auto;
  border-radius: 100%;
  margin-top: 16px;

}
.wrapper{
  margin-top: 18px;
  background-color: #93D94E;
  width: 60%;
  border-radius: 12px;
  margin: 0 auto;
  overflow: hidden;
}
</style>
