<template>
  <div class="hello">
    <div v-for="(item, index) in products" :key="index">
      <div :id="item.id" :hot="item.hot" >
          <img :src='item.image'>
          <div>
            <h1>Tên sản phẩm {{item.name}}</h1>
            <p>Giá sản phẩm {{item.price}}</p>
            <p>Ngày SX {{item.publicDate}}</p>
          </div>
      </div>
    </div>
    <div class="">
        <h1>Hot product</h1>
      <div v-for="(item, index) in showProductHot" :key="index">
          <div>
            <img :src='item.image'>
          <div>
            <h1>Tên sản phẩm {{item.name}}</h1>
            <p>Giá sản phẩm {{item.price}}</p>
            <p>Ngày SX {{item.publicDate}}</p>
          </div>
      </div>
    </div>
      <div class="">
        <h1>Max</h1>
        {{_showH[0].name}}
        <img :src='_showH[0].image'>
          <div>
            <h1>Tên sản phẩm {{_showH[0].name}}</h1>
            <p>Giá sản phẩm {{_showH[0].price}}</p>
            <p>Ngày SX {{_showH[0].publicDate}}</p>
          </div>
      </div>
      <div class="">
        <h1>Min</h1>
        <img :src='_showL[0].image'>
          <div>
            <h1>Tên sản phẩm {{_showL[0].name}}</h1>
            <p>Giá sản phẩm {{_showL[0].price}}</p>
            <p>Ngày SX {{_showL[0].publicDate}}</p>
          </div>
      </div>
  </div>
</div>

</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
 return {
   bag: [],
   hotProduct: [],
   cart: [],
   products: [
     {
       id: 1,
       name: "PS5",
       price: 5555,
       publicDate: "05-05-2021",
       image:
         "https://cdn.vjshop.vn/hightech/may-choi-game/ps5/sony-ps-5-1.jpg",
       hot: true,
     },
     {
       id: 2,
       name: "PS4",
       price: 4444,
       publicDate: "04-04-2021",
       image:
         "https://gmedia.playstation.com/is/image/SIEPDC/ps4-slim-image-block-01-en-24jul20?$native--t$",
       hot: true,
     },
     {
       id: 3,
       name: "PS3",
       price: 3333,
       publicDate: "03-03-2021",
       image:
         "https://game.haloshop.vn/image/catalog/blogs/ps3-co-con-dang-mua/ps3-co-con-dang-mua-21.jpg",
       hot: false,
     },
   ],
   paymentMethods: [
     { text: "COD", value: 1 },
     { text: "Banking", value: 2 },
     { text: "Ứng dụng bên thứ 3", value: 3 },
   ],
   selectedPayment: 2,
 };
},
computed: {
  showProductHot() {
    return this.products.filter(x => x.hot)
  },
  _showL() {
    return this.products.filter(x => Math.min(x.price))
  },
  _showH() {
    return this.products.filter(x => Math.max(x.price))
  }
}
,
methods: {
},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*, *::before, *::after {
  box-sizing: border-box;
}
* {
  margin: 0;
}

html, body {
  height: 100%;
}
body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
  -webkit-tap-highlight-color: rgba(0,0,0,0);
}

img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}
input, button, textarea, select {
  font: inherit;
  outline: none;
  border: none;
}
p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}
img {
  width: 200px;
  height: 200px;
}
</style>
