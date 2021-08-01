<template>
  <Header/>
  <Advantages v-bind:advantages="advantages"/>
  <Slider v-bind:slider="slider"/>
  <Shopping
      :popUpVisible="popUpVisible"
      @open-form="openForm"
  />
  <shopping-form
      :popUpVisible="popUpVisible"
      :submitStatus="submitStatus"
      @close-form="closeForm"
      @on-submit = 'onSubmit'
  />
  <Footer/>
</template>

<script>
import Header from '@/components/header/Header'
import Advantages from "@/components/advantages/Advantages";
import Slider from "@/components/slider/Slider";
import Footer from "@/components/footer/Footer";
import Shopping from "@/components/shopping/Shopping";
import ShoppingForm from "@/components/shopping/ShoppingForm";

export default {
  name: 'App',
  data(){
    return{
      advantages:[
        {id:1, title: 'Нет контакта с посторонними людьми', subTitle: 'Заказ формируется из товаров, до которых никто не дотрагивался, как это возможно на полках обычного магазина. Фрукты и овощи отбираются сборщиком вручную.', img:'1.png'},
        {id:2, title: 'Заморозка 1 раз', subTitle: 'Продукты замораживаются однократно и поддерживаются в этом состоянии, пока не будут доставлены к вам.', img:'2.png'},
        {id:3, title: 'Профессиональные морозильные камеры', subTitle: 'Товар хранится в промышленных холодильных и морозильных зонах с оптимальными температурными режимами для разных товаров: овощей, фруктов, масла и т. д.', img:'3.png'},
        {id:4, title: 'Разделка мяса и рыбы под заказ', subTitle: 'Мясо и рыба разделываются непосредственно для вас, а при транспортировке хранятся в специальных боксах с низкой температурой.', img:'4.png'},
        {id:5, title: 'Своя пекарня', subTitle: 'Знак «Печём сами» на карточках товаров означает, что мы привезём вам свежеиспечённый тёплый хлеб.', img:'5.png'},
        {id:6, title: 'Работаем с 1995 года', subTitle: 'Мы занимаемся продуктами с 1995 года — все процессы хранения и доставки отточены до мелочей.', img:'6.png'}
      ],
      slider:[
        {id:1, title:'Привезём точно по списку', subtitle:'Сборщик берëт с собой наручный терминал, на котором он видит весь список покупок для каждого заказа.', img:'1.jpg'},
        {id:2, title:'Собираем быстро и эффективно', subtitle:'Для улучшения эргономики пространства товары размещены от тяжëлых к лëгким, находящимся уже в конечной зоне упаковки.', img:'2.jpg'},
        {id:3, title:'За свежесть и качество отвечаем', subtitle:'Выделены специальные зоны, в том числе холодная и морозильная.', img:'3.jpg'},
        {id:4, title:'Шампунь не положат рядом с рыбой', subtitle:'Собираем и упаковываем ваш заказ с заботой: соблюдаем принципы товарного соседства и учитываем вес товара.', img:'4.jpg'},
        {id:5, title:'Довезëм в сохранности даже яйца', subtitle:'Бережно транспортируем контейнеры, фиксируя их стяжными ремнями. Системы охлаждения поддерживают температурный режим.', img:'5.jpg'}
      ],
      popUpVisible:false,
      mail:'',
      submitStatus: false
    }
  }, components: {
    Header, Advantages, Slider, Shopping, Footer, ShoppingForm
  }, methods:{
    closeForm(){
      this.popUpVisible = false
      this.submitStatus = false
    },
    openForm(){
      this.popUpVisible = true
    },
    async onSubmit(x){
      // if(x.trim()){
      //   console.log('if', x.trim())
      // }else{
      //   console.log('else', x.trim())
      // }
      this.mail = x
      try {
        await fetch('https://jsonplaceholder.typicode.com/posts', {
          method: 'POST',
          body: JSON.stringify({
            date: this.mail,
            dateId: Date.now(),
          }),
          headers: {
            'Content-type': 'application/json; charset=UTF-8',
          },
        })
            .then((response) => {
              const status = response.status;

              if (status >= 200 && status < 300) {
                this.submitStatus = true
                console.log('success')
              } else if (status === 404) {
                this.submitStatus = false
                console.log('error 404')
              }
              return response.json();

            })
            .then((json) => console.log(json));

      }catch (error) {
        console.log(error)
      }

    }
  }
}
</script>

<style>
@font-face {
  font-family: "RotondaC";
  font-weight: 400;
  font-style: normal;
  font-display: auto;
  unicode-range: U+000-5FF;
  src: url("./assets/fonts/RotondaCRegular.woff") format("woff");
}
@font-face {
  font-family: "RotondaC";
  font-weight: 700;
  font-style: normal;
  font-display: auto;
  unicode-range: U+000-5FF;
  src: url("./assets/fonts/RotondaBoldRegular.woff") format("woff");
}
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

#app {
  font-family: "RotondaC", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #f7f7f7;
}
.container {
  width: 916px;
}
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  border: 0;
  clip: rect(0 0 0 0);
}
@media (max-width: 1024px){


}
@media (max-width: 320px){
  .container {
    width: 301px;
  }

}
</style>
