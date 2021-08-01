<template>
  <li class="slider__item slide" :style="{'left': '-' + (100 * currentSlideIndex) + '%'}">
    <div class="slide__num">{{sliderItem.id}}</div>
    <img class="slide__img" :src="require('@/assets/images/slider/' + sliderItem.img)" alt="Изображение из раздела {{sliderItem.title}}">
    <h3 class="slide__title">{{sliderItem.title}}</h3>
    <p class="slide__subtitle">{{sliderItem.subtitle}}</p>
  </li>
</template>

<script>
export default {
  name: "SliderItem",
  props:{
    sliderItem:{
      type:Object,
      required:true
    },
    currentSlideIndex:{
      type: Number,
      required: true
    }
  }
}
</script>

<style scoped>
.slide{
  width: 640px;
  height: 450px;
  padding: 40px 40px 0 40px;
  background: #fff;
  box-shadow: 0px 0px 40px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  display: grid;
  grid-template-rows: min-content min-content min-content;
  position: relative;
  transition: 200ms ease-in;
}
.slider__item{}
.slide__num{
  position: absolute;
  top: 33px;
  left: 33px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: #fff;
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 46px;
  text-align: center;
  color: #7db945;
}
.slide__img{
  margin-bottom: 28px;
}
.slide__title{
  width: 500px;
  font-style: normal;
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  color: #26303B;
}
.slide__subtitle{
  width: 500px;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #26303B;
}

@media (max-width: 320px){
  .slide{
    width: 280px;
    height: 350px;
    padding: 20px 20px 0 20px;
    display: grid;
  }
  .slider__item{}
  .slide__num{
    position: absolute;
    top: 13px;
    left: 13px;
    width: 40px;
    height: 40px;
    font-size: 16px;
    line-height: 46px;
  }
  .slide__img{
    width: 240px;
    margin-bottom: 28px;
  }
  .slide__title{
    width: 240px;
    font-style: normal;
    font-weight: 700;
    font-size: 14px;
    line-height: 22px;
    color: #26303B;
  }
  .slide__subtitle{
    width: 240px;
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 22px;
    color: #26303B;
  }

}
</style>