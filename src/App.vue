<template>
  <div>
    <h4>{{ product[0] }}</h4>
    <p>50 만원</p>
  </div>
  <div>
    <h4>{{ product[1] }}</h4>
    <p>가격은 아무거나</p>
  </div>
  <div>
    <h4>{{ product[2] }}</h4>
    <p>가격은 아무거나</p>
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