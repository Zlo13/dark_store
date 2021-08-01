<template>
  <div class="popup" v-if="popUpVisible">
    <div class="popup__content">
      <form @submit.prevent="$emit('on-submit', mail)" class="shopping-form">
        <h2 class="shopping-form__title">Shopping form</h2>
        <input class="shopping-form__input" type="email" placeholder="e-mail" v-model="mail">
        <button class="shopping-form__close" @click="$emit('close-form')">&times;</button>
        <button class="shopping-form__send">Отправить</button>
        <div class="shopping-form__ok" v-if="submitStatus">Спасибо!!!</div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "shoppingForm",
  props:{
    popUpVisible:{
      type: Boolean,
      default: false
    },
    mail:{
      type:String,
      default: ''
    },
    submitStatus:{
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.popup {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  display: flex;
}
.popup__content {
  position: relative;
  margin: auto;
  background: white;
  border-radius: 10px;
  min-height: 50px;
  min-width: 300px;
  padding: 20px;
}
.shopping-form{
  display: grid;
  grid-template: min-content min-content min-content/ 1fr min-content;
  grid-row-gap: 1em;
}
.shopping-form__title{
  justify-self: start;
  align-self: center;
}
.shopping-form__input{
  grid-column: 2 span;
  outline: none;
  box-sizing: border-box;
  font-size: 18px;
  padding: 0.5em 1em;
  width: 100%;
  border: none;
  border-bottom: 2px solid #ccc;
}
.shopping-form__input:focus{
  border-bottom: 2px solid #7db945;
}
.shopping-form__close{
  grid-row: 1/2;
  grid-column: 2/3;
  outline: none;
  font-weight: 700;
  font-size: 36px;
  line-height: 46px;
  text-align: center;
  color: tomato;
  border: none;
  background-color: transparent;
  cursor: pointer;
  transition: 200ms ease-in;
}
.shopping-form__close:hover{
  transform: rotateZ(360deg);
}
.shopping-form__send{
  grid-column: 2 span;
  padding: 0.3em 1em;
  border: none;
  background-color: #7db945;
  border-radius: 0.3em;
  font-weight: 700;
  font-size: 18px;
  text-align: center;
  color: #fff;
  cursor: pointer;
}
.shopping-form__ok{

  grid-column: 2 span;
  color: #7db945;
  font-size: 18px;

}
</style>