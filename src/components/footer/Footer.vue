<template>
  <footer class="footer">
    <div class="footer__container container">
      <img
          class="footer__logo"
          src="@/assets/images/logo.png"
          alt="Логотип магазина Перекресток."
      />
      <ul class="phone phone__list">
        <li class="phone__item">
          <div class="phone__title" >Москва</div>
          <a class="phone__link" href="tel:+74957975777">+7 495 797-57-77</a>
        </li>
        <li class="phone__item">
          <div class="phone__title">Санкт-Петербург</div>
          <a class="phone__link" href="tel:+78123859955">+7 812 385-99-55</a>
        </li>
      </ul>
      <ul class="social social__list">
        <li class="social__item">
          <a href="" class="social__link social__link--fb" aria-label="Фейсбук"></a>
        </li>
        <li class="social__item">
          <a href="" class="social__link social__link--vk" aria-label="ВКонтакте"></a>
        </li>
        <li class="social__item">
          <a href="" class="social__link social__link--in" aria-label="Инстаграм"></a>
        </li>
        <li class="social__item">
          <a href="" class="social__link social__link--ok" aria-label="Одноклассники"></a>
        </li>
      </ul>

    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style scoped>
ul{
  list-style: none;
  padding: 0;
}
.footer{
  height: 270px;
  /*background-color: #2c3e50;*/
  background: linear-gradient(0deg, #043E44, #043E44), #CBE07D;
}
.footer__container{
  margin: 0 auto;
  height: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: min-content 1fr;
}
.footer__logo{
  width: 130px;
  grid-column: 1/3;
  padding: 47px 0 15px 0;
}

.phone{}
.phone__list{
  display: grid;
  grid-template-columns: 1fr 1fr;
  justify-items: start;
  text-align: left;
}
.phone__item{

}
.phone__title{
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 36px;
  color: #fff;
}
.phone__link{
  text-decoration: none;
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 36px;
  color: #fff;

}

.social{}
.social__list{
  display: grid;
  grid-template-columns: repeat(4,31px);
  justify-content: end;
  grid-gap: 40px;
}
.social__item{
margin-top: 20px;
}
.social__link{
  width: 31px;
  height: 31px;
  display: block;

}
.social__link--fb{
  background: url("../../assets/images/f.png") no-repeat center;
}
.social__link--vk{
  background: url("../../assets/images/vk.png") no-repeat center;
}
.social__link--in{
  background: url("../../assets/images/in.png") no-repeat center;
}
.social__link--ok{
  background: url("../../assets/images/ok.png") no-repeat center;
}
</style>