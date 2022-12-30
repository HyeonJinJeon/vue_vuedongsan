<template>
  <div v-if="modalWindow == true" class="black-bg">
    <div class="white-bg">
      <h4>{{oneRooms[clickRoom].title}}</h4>
      <img :src="oneRooms[clickRoom].image"/>
      <p>
        {{oneRooms[clickRoom].price}}원<br>
        {{oneRooms[clickRoom].content}}
      </p>
      <Discount/>
<!--      <button @click="modalWindow=false">닫기</button>-->
    </div>
  </div>
</template>
<script>
import Discount from './Discount.vue';
export default {
  name : 'Modal',
  props : {
    oneRooms : Array,
    clickRoom : Number,
    modalWindow : Boolean
  },
  components: {
    Discount : Discount,
  }
}

</script>
<style>

</style>