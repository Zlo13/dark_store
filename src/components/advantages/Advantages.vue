<template>
<section class="advantages">
  <div class="advantages__container container">
    <h2 class="advantages__title">
      Преимущества даркстора
    </h2>
    <ul class="advantages__list">
      <Advantage
          v-for="advantage in advantages"
          :key="advantage.id"
          v-bind:advantage="advantage"
          @advantage-click="foo"
      />
    </ul>
  </div>

</section>
</template>

<script>
import Advantage from "@/components/advantages/Advantage";
export default {
  name: "Advantages",
  components:{
    Advantage
  },
  props:{
    advantages:{
      type: Array,
      required:true
    }
  },
  methods:{
    foo(x){
      console.log(x)
    }
  }
}
</script>

<style scoped>
.advantages__container{
  margin: 0 auto;
}
.advantages__title{
  margin-bottom: 40px;
  font-style: normal;
  font-weight: bold;
  font-size: 36px;
  line-height: 60px;
  text-align: center;
  color: #26303B;
}
.advantages__list{
  list-style: none;
  padding: 0;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 30px;
  margin-bottom: 130px;
}
@media (max-width: 1024px){


}
@media (max-width: 320px){
  .advantages__title{
    font-size: 26px;
    line-height: 32px;
    margin-bottom: 20px;
  }
  .advantages__list{
    grid-template-columns: 1fr 1fr;
    grid-gap: 9px;
    margin-bottom: 50px;
  }
}
</style>