<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src=" 원룸들[누른거].image" style="width:100%">
      <h4>{{  원룸들[누른거].title  }}</h4>
      <p>{{원룸들[누른거].content}}</p>
      <input v-model.number="month">
      <p> {{month}}개월 선택함 : {{원룸들[누른거].price * month}} 원</p>
      
      <button @click="closeModal">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name:'Modal',
    data(){
      return{
        month : 1,

      }
    },
    watch:{
      month(a){
        // 사용자가 month에 입력한 데이터가 13보다 크면 경고문 띄우기기
        if(a > 13 ){
          alert('13이상 입력하지마셈');
        }
        else if(isNaN(a) == true){
          alert('글자입력하지마셈');
          this.month =1;
        }

      },
    },

    beforeUpdate() {
      if(this.month ==2){
        alert('2개월은 너무 적음... 안팝니다.')
      }
    },

    props:{
        원룸들: Array,
        누른거: Number,
        모달창열렸니:Boolean,
    },
    methods:{
      closeModal(){
        this.$emit('closeModal')
      }
    }
}
</script>

<style>
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
</style>