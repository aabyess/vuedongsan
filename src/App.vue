<template>
  <div>
    {{logo }}
    <h4 class="red" :style="스타일">xx 원룸</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>xx 원룸</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  
</template>

<script>

export default {
  name : 'App',
  data() {
    return{
      product :[ '역사동원룸', '천호동원룸','마포구원룸'],
    }
  },
  components : {
  }
}
</script>

<style>

</style> 