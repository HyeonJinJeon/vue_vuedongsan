<template>

  <div class="black-bg" v-if="modalWindow == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modalWindow=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in allMenu" :key="menu">{{ menu }}</a>

  </div>

  <div v-for="(data, i) in oneRooms" :key="i">
    <img :src="oneRooms[i].image" class="room-img">
    <h4 @click="modalWindow = true">{{ oneRooms[i].title }} </h4>
    <p>{{ oneRooms[i].price }}원</p>
    <button @click="increase(i)">허위매물 신고</button>
    <span> 신고 누적수 : {{num[i]}}</span>
  </div>
</template>

<script>

import data from './assets/data';

export default {
  name: 'App',
  data(){
    return {
      oneRooms : data,
      modalWindow : false,
      num : [0, 0, 0, 0, 0, 0],
      price1 : 80,
      price2 : 70,
      price3 : 90,
      products : ['역삼동원룸', '천호동원룸','마포구원룸'],
      allMenu : ['Home', 'Products', 'About']
    }
  },
  methods : {
    increase(i){
      this.num[i]++;
    }
  },
  components: {
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
