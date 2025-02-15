<template>

<!-- 'CTRL + /' 주석처리 -->

  <!-- <div class="start" :class="{end : 모달창열렸니}"> -->
  <Transition name="fade">
    <Modal @closeModal="모달창열렸니 = false"
    :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>
  </Transition>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>

  <Discount v-if="showDiscount == true" />


  <button @click="priceSort">가격순정렬</button>
  <button @click="sortBack">되돌리기기</button>
  <button @click="highPriceSort">가격역순정렬</button>


  <Card @openModal="모달창열렸니 = true; 누른거 = $event" 
  :원룸="원룸들[i]" v-for="(작명,i) in 원룸들" :key="작명" />

  <!-- <Card :원룸="원룸들[1]" />
  <Card :원룸="원룸들[2]" />
  <Card :원룸="원룸들[3]" />
  <Card :원룸="원룸들[4]" />
  <Card :원룸="원룸들[5]" /> -->
  
  

  



 
</template>

<script>
import data from './assets/oneroom';
import Card from './Card.vue';
import Discount from './Discount.vue';
import Modal from './Modal.vue';

// setTimeout(function(){
//   실행할 코드
// }, 2000);

// setInterval(() => {
  
// }, interval);

export default {
  name : 'App',
  data() {
    return{
      showDiscount : true,
      원룸들오리지널 : [...data],
      누른거: 0,
      원룸들 : data,
      모달창열렸니 : false,
      신고수 : [0,0,0],
      메뉴들 : ['Home', 'Shop','About'],
      amount : 30,
    }
  },
  methods:{
    increase(){
      this.신고수++;
    },
    priceSort(){
      this.원룸들.sort(function(a,b){
        return a.price - b.price;
      })
    }, 
    sortBack(){
      this.원룸들 = [...this.원룸들오리지널];
    },
    highPriceSort(){
      this.원룸들.sort(function(a,b){
        return b.price -a.price;
      })
    },
  },

  mounted(){
    setInterval(() => {
      this.amount--;
    }, 1000);
  },

  // mounted(){
  //   setTimeout(()=>{
  //     this.showDiscount = false;
  //   }, 2000);
  // },


  components : {
    Discount,
    Modal,
    Card,
  }
}
</script>

<style>
/* .start{
  opacity: 0;
  transition: all 1s;

}
.end{
  opacity: 1;
} */

.fade-enter-from {
  transform: translateY(-1000px);

}
.fade-enter-active {
  transition: all 1s;

}
.fade-enter-to {
  transform: translateY(0px);

}

.fade-leave-from {
  opacity: 1;

}
.fade-leave-active {
  transition: all 1s;

}
.fade-leave-to {
  opacity: 0;
  
}


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