<template>
  <section class="shopping">
    <div class="sopping__container container">
      <h2 class="visually-hidden">Shopping</h2>
      <div class="shopping__bonus bonus">
        <div class="bonus__circle">
          <img :src="require('@/assets/images/shopping/discount.svg')" alt="Иконка скидки" class="bonus__img">
        </div>

        <h3 class="bonus__title">Скидка <span>1500 ₽</span></h3>
        <p class="bonus__subtitle"><span>–500 ₽</span> на первые три заказа по промокоду NEW</p>
      </div>
      <div class="shopping__plus">+</div>
      <div class="shopping__bonus bonus">
        <div class="bonus__circle">
          <img :src="require('@/assets/images/shopping/shipping.svg')" alt="Иконка доставки." class="bonus__img">
        </div>

        <h3 class="bonus__title">Бесплатная <span>доставка</span></h3>
        <p class="bonus__subtitle">первого заказа</p>
      </div>
      <button class="shopping__btn" @click="$emit('open-form')">К покупкам</button>
    </div>
  </section>

</template>

<script>
export default {
  name: "Shopping"
}
</script>

<style scoped>
.shopping{
  display: block;
  width: 100%;
  background-color: #fff;
}
.sopping__container{
  margin: 0 auto;
  padding-bottom: 100px;
  background-color: #fff;
  display: grid;
  grid-template: min-content min-content / 1fr min-content 1fr;
  justify-items: center;
  align-items: center;
  grid-row-gap: 50px;
}
.shopping__bonus{}
.bonus{
  margin-top: 60px;
  width: 380px;
  height: 217px;
  background: #fff;
  border: 1px solid #d0d4cd;
  box-sizing: border-box;
  display: grid;
  grid-template: 1fr 1fr/ 130px 250px;

}

.bonus__circle{
  justify-self: center;
  align-self: center;
  display: flex;
  width: 70px;
  height: 70px;
  border-radius: 50%;
  background-color: #7DB945;
}
.bonus__img{
  margin: auto;
  width: 50px;
  height: 50px;
}
.bonus__title{
  padding-right: 50px;
  align-self: end;
  justify-self: start;
  font-style: normal;
  font-weight: 700;
  font-size: 36px;
  line-height: 46px;
  color: #26303B;
  text-align: left;
}
.bonus__title>span{
  color: #7DB945;
}
.bonus__subtitle{
  text-align: left;
  align-self: start;
  justify-self: start;
  grid-column: 2/3;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #26303B;
}
.bonus__subtitle>span{
  font-weight: 700;
}
.shopping__plus{
  font-style: normal;
  font-weight: 700;
  font-size: 36px;
  line-height: 46px;
  text-align: center;
  color: #26303B;
}
.shopping__btn{
  grid-column: 3 span;
  border: none;
  width: 340px;
  height: 70px;
  background-color: #7DB945;
  border-radius: 10px;
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 36px;
  text-align: center;
  letter-spacing: 0.01em;
  color: #fff;
  cursor: pointer;
}
</style>