<template>
  <li class="advantages__item advantage" v-on:click="$emit('advantage-click',advantage.id)">

    <img class="advantage__img" :src="require('@/assets/images/advantages/' + advantage.img)" alt="Иконка раздела {{advantage.title}}.">
    <h3 class="advantage__title">{{advantage.title}}</h3>
    <p class="advantage__subtitle">{{advantage.subTitle}}</p>
  </li>

</template>

<script>
export default {
  name: "Advantage",
  props:{
    advantage:{
      type: Object,
      required:true
    }
  }
}
</script>

<style scoped>
.advantages__item{
  padding: 18px;
  height: 390px;
  background: #fff;
  box-shadow: 0 0 37px rgba(230, 231, 235, 0.09);
  border-radius: 10px;
  display: grid;
  grid-template-rows: 150px 60px min-content;
  transition: 200ms ease-in;
  cursor:pointer;
}
.advantages__item:hover{
  box-shadow: 14px 14px 19px 7px rgba(230, 231, 235, 0.9);
}
.advantage__img{
  justify-self: center;
  align-self: center;
}
.advantage__title{
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  text-align: center;
  color: #26303B;
}
.advantage__subtitle{
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  text-align: center;
  color: #26303B;
}
@media (max-width: 1024px){


}
@media (max-width: 320px){
  .advantages__item{
    padding: 5px;
    height: 174px;
    border-radius: 5px;
    display: grid;
    grid-template-rows: 69px 1.5em min-content;
  }
  .advantage__img{
    width: 40%;
    justify-self: center;
    align-self: center;
  }
  .advantage__title{
    font-size: 8px;
    line-height: 11px;
  }
  .advantage__subtitle{
    font-size: 8px;
    line-height: 11px;
  }

}
</style>