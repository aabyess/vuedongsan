<template>
    <div>
      <img :src="원룸.image" class="room-img">
      <h4 @click="send"> {{원룸.title}} </h4>
      <p>{{원룸.price}} 원</p>
     </div>
</template>

<script>
export default {
    name :'Card',
    props:{
        원룸 : Object,
    },
    methods:{
        send(){
            this.$emit('openModal', this.원룸.id)
        }
    }
}
</script>

<style>

</style>