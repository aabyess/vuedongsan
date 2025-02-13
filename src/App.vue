<template>

<!-- CTRL +/ 주석처리 -->


  <Modal :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>


  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>

  <Card :원룸="원룸들[i]" v-for="(작명,i) in 원룸들" :key="작명" />

  <!-- <Card :원룸="원룸들[1]" />
  <Card :원룸="원룸들[2]" />
  <Card :원룸="원룸들[3]" />
  <Card :원룸="원룸들[4]" />
  <Card :원룸="원룸들[5]" /> -->
  
  <Discount/>




 
</template>

<script>
import data from './assets/oneroom';
import Card from './Card.vue';
import Discount from './Discount.vue';
import Modal from './Modal.vue';

export default {
  name : 'App',
  data() {
    return{
      누른거: 0,
      원룸들 : data,
      모달창열렸니 : false,
      신고수 : [0,0,0],
      메뉴들 : ['Home', 'Shop','About'],
      products : [ '역사동원룸', '천호동원룸','마포구원룸'],
    }
  },
  methods:{
    increase(){
      this.신고수++;
    }
  },
  components : {
    Discount,
    Modal,
    Card,
  }
}
</script>

<style>
body{
  margin:0
}
div{
  box-sizing: border-box;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding :10px;
}

.room-img{
  width: 100%;
  margin-top:40px;
}
</style> 