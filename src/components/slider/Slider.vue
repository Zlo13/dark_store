<template>
  <section class="slider">
    <div class="slider__container container">
      <h2 class="slider__title">Взгляните на процесс сборки своими глазами</h2>
        <ul class="slider__list">
          <SliderItem
              :currentSlideIndex="currentSlideIndex"
              v-for="sliderItem in slider"
              :key="sliderItem.id"
              :sliderItem="sliderItem"
          />
        </ul>
      <div class="arrow arrow__left" @click="prevSlide"></div>
      <div class="arrow arrow__right" @click="nextSlide"></div>
    </div>
  </section>
</template>

<script>
import SliderItem from "@/components/slider/SliderItem";
export default {
  name: "Slider",
  components:{SliderItem},
  props:{
    slider:{
      type:Array,
      required:true
    }
  },
  data(){
    return{
      currentSlideIndex:0
    }

  },
  methods:{
    prevSlide(){
      if(this.currentSlideIndex > 0){
        this.currentSlideIndex--
      }
    },
    nextSlide(){
      if(this.currentSlideIndex < this.slider.length - 1){
        this.currentSlideIndex++
      }
    }
  }
}
</script>

<style scoped>
.slider{
  padding-bottom: 80px;
}
.slider__container{
  margin: 0 auto;
  display: grid;
  justify-content: center;
  grid-column-gap: 30px;
  grid-template-columns: min-content min-content min-content;
  grid-template-rows: min-content min-content;

}
.slider__title{
  margin-bottom: 28px;
  grid-column: 3 span;
  font-style: normal;
  font-weight: 700;
  font-size: 36px;
  line-height: 46px;
  text-align: center;
  color: #26303B;
}
.slider__list{
  grid-column-start: 2;
  width: 640px;
  list-style: none;
  padding: 0;
  display: flex;
  overflow: hidden;
}
.arrow{
  width: 20px;
  height: 40px;
  align-self: center;
  cursor:pointer;
}
.arrow__left{
  grid-column-start: 1;
  grid-row-start: 2;
  background: url("../../assets/images/slider/arrow_l.svg") no-repeat center;
}
.arrow__right{
  grid-column-start: 3;
  background: url("../../assets/images/slider/arrow_r.svg") no-repeat center;
}
@media (max-width: 1024px){
  .slider__title{
    width: 500px;
    justify-self: center;
  }
}
@media (max-width: 320px){
  .slider{
    padding-bottom: 80px;
  }
  .slider__container{
    margin: 0 auto;
    display: grid;
    justify-content: center;
    grid-column-gap: 0;
    grid-template-columns: min-content min-content;
    grid-template-rows: min-content min-content min-content;

  }
  .slider__title{
    width: 300px;
    grid-column: 2 span;
    font-size: 26px;
    line-height: 32px;

  }
  .slider__list{
    /*grid-column-start: 2;*/
    grid-column: 2 span;
    width: 280px;
    list-style: none;
    padding: 0;
    display: flex;
    overflow: hidden;
  }
  .arrow{
    padding: 100px 30px 0 30px;
    width: 14px;
    height: 29px;
    align-self: center;
    cursor:pointer;
  }
  .arrow__left{
    grid-column: 1/2;
    grid-row: 3/4;
    background: url("../../assets/images/slider/arrow_l.svg") no-repeat center;
    justify-self: end;
  }
  .arrow__right{
    grid-column: 2/3;
    grid-row: 3/4;
    background: url("../../assets/images/slider/arrow_r.svg") no-repeat center;
  }

}
</style>