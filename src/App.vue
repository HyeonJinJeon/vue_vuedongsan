<template>
  <div>
    <Modal :oneRooms="oneRooms" :clickRoom="clickRoom" :modalWindow="modalWindow"/>
  </div>
  <div class="menu">
    <a v-for="menu in allMenu" :key="menu">{{ menu }}</a>
  </div>

  <Discount/>
  <Card oneRoom="oneRooms[1]"/>
  <Card/>
  <Card/>
  <Card/>
  <Card/>
  <Card/>

  <Card @openmodal="modalWindow=true" v-for="(data, i) in oneRooms" :key="i" :oneRooms="oneRooms"/>
<!--  <Card-->
<!--        :oneRooms="oneRooms" :modalWindow="modalWindow"-->
<!--        :clickRoom="clickRoom" :increse="increase" :num="num"-->
<!--  />-->
</template>

<script>

import data from './assets/data';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data(){
    return {
      clickRoom : 0,
      oneRooms : data,
      modalWindow : false,
      num : [0, 0, 0, 0, 0, 0],
      price1 : 80,
      price2 : 70,
      price3 : 90,
      allMenu : ['Home', 'Products', 'About']
    }
  },
  methods : {
    increase(i){
      this.num[i]++;
    }
  },
  components: {
    Discount : Discount,
    Modal : Modal,
    Card : Card,
  }
}
</script>

<style>
body {
  margin : 0
}
div {
  box-sizing: border-box;
}
.discount {
  background: #eee;
  padding:10px;
  margin:10px;
  border-radius: 5px;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.room-img{
  width: 100%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
 }
</style>
