<template>
  <div>
    <img :src="oneRoom.image" class="room-img">
    <h4> {{ oneRoom.title }}</h4>
    <p>{{ oneRoom.price }}원</p>
<!--    <button @click="increase(i)">허위매물 신고</button>-->
<!--    <span> 신고 누적수 : {{num[i]}}</span>-->
  </div>
</template>
<script>
export default {
  name: 'Card',
  props : {
    oneRoom : Object,
    // clickRoom : Number,
    // modalWindow : Boolean,
    // num : Array,
  },
  data() {
    return{

    }
  },
  methods : {
    increase(i){
      this.num[i]++;
    }
  },
}
</script>
<style>

</style>
