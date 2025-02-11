<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>


  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>



  <div v-for="(a,i) in 원룸들" :key="i">
    <img :src="a.image" class="room-img">
    <h4 @click="모달창열렸니 =true">{{a.title}}</h4>
    <p>{{a.price}}</p>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>가격은 아무거나</p>
    <button @click="신고수[1]++">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>가격은 아무거나</p>
    <button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span>
  </div>
</template>

<script>
import data from './assets/oneroom';
export default {
  name : 'App',
  data() {
    return{
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

.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding:20px;
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