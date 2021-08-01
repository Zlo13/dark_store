<template>
  <header class="header">
    <div class="header__container container">
      <img
        class="header__logo"
        src="@/assets/images/logo.png"
        alt="Логотип магазина Перекресток."
      />
      <h1 class="header__title">Что такое даркстор?</h1>

      <p class="header__subtitle">
        Это магазин-склад без покупателей.
        Именно здесь, а не в розничном
        магазине собирают ваши заказы.
      </p>
      <img
        class="header__swype-logo"
        src="@/assets/images/swype.png"
        alt="иконка свайпа вниз."
      />
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header'
};
</script>

<style scoped>
.header {
  width: 100%;
  height: 530px;
  padding-top: 53px;
  background: url("../../assets/images/header/header_img.jpg") no-repeat bottom;
  background-size: cover;
  display: flex;
  justify-content: center;
  margin-bottom: 100px;
}


.header__container {
  display: grid;
  grid-template-rows: min-content min-content min-content;
}
.header__logo{
  width: 150px;
  margin-bottom: 120px;
}
.header__title {
  text-align: left;
  font-weight: 700;
  font-size: 54px;
  letter-spacing: 0.02em;
  text-transform: uppercase;
  color: #FFFFFF;
}

.header__subtitle {
  width: 510px;
  margin-bottom: 35px;
  text-align: left;
  font-weight: 400;
  font-size: 26px;
  line-height: 44px;
  letter-spacing: 0.02em;
  color: #FFFFFF;
}
.header__swype-logo{
  width: 140px;
  justify-self: center;
}
@media (max-width: 1024px){
  .header__title {
    font-size: 40px;
    line-height: 44px;
  }
  .header__subtitle {
    width: 380px;
    font-size: 20px;
    line-height: 32px;
  }
  .header__logo{
    margin-bottom: 100px;
  }
  .header {
    height: 466px;
    margin-bottom: 65px;
  }
}
@media (max-width: 320px){
  .header__title {
    text-align: center;
    width: 150px;
    font-size: 28px;
    line-height: 36px;
    margin-bottom: 20px;
  }
  .header__subtitle {
    text-align: center;
    width: 270px;
    font-size: 16px;
    line-height: 22px;
  }
  .header__logo{
    width: 100px;
    margin-bottom: 60px;
  }
  .header {
    height: 357px;
    padding-top: 40px;
    margin-bottom: 40px;
  }
  .header__swype-logo{
    display: none;
  }
  .header__container {
    display: grid;
    grid-template-columns: 320px;
    grid-template-rows: min-content min-content min-content;
    justify-content: center;
    justify-items: center;
  }

}
</style>