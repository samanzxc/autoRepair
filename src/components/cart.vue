<script setup>
import { ref } from 'vue'
import {isActiveCart} from './globalVar.js'


const props = defineProps({
  cart: Array,
  items: Array,
  addToCart: Function,
  resultPrice: Number
})

</script>

<template>
  <div class="cart" :class="{ active: isActiveCart }">
    <div class="empty" v-show="!props.cart.length">Корзина пуста</div>
    <img src="/src/assets/image/close.png" alt="" class="close" @click="isActiveCart = !isActiveCart" />
    <div class="wrapp">
    <div class="wrapp__item">
      <div class="item" v-for="(item, index) in props.cart" :key="index">
        <div class="item__name">
          <b>{{ item.itemName }}</b>
        </div>
        <div class="item__price">
          <p>Стоимость:</p>
          <span class="dec"></span><b>{{ item.itemPrice }}₽</b>
        </div>
        <button class="btn remove" @click="props.addToCart(item)">Убрать</button>
      </div>
    </div>
    <div class="finish">
      <div class="all__price">
        <p>Общая Стоимость:</p> <span class="dec"></span><b>{{ props.resultPrice }}₽</b>
      </div>
      <button class="btn">Оплатить</button>
    </div>
</div>
  </div>
  <div class="cart__btn" @click="isActiveCart = !isActiveCart" v-show="!isActiveCart">
    <div class="card__num">{{ props.cart.length }}</div>
    <img
      src="https://cdn1.iconfinder.com/data/icons/line-awesome-vol-5/32/shopping-cart-solid-1024.png"
      alt=""
    />
  </div>
</template>

<style scoped>
.cart {
  width: 350px;
  position: fixed;
  right: -1000px;
  top: 0;
  bottom: 0;
  background-color: #fff;
  z-index: 2;
  border-left: 2px rgba(0, 0, 0, 0.116) solid;
  padding: 15px;
  transition: 0.4s;
  padding-bottom: 40px;
}
.active {
  right: 0;
}
.close {
  background-color: black;
  width: 35px;
  border-radius: 5px;
  cursor: pointer;
  margin-bottom: 50px;
}
.cart__btn {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  position: fixed;
  right: 40px;
  bottom: 40px;
  z-index: 2;
  background-color: #ebebeb;
  cursor: pointer;
}
.card__num {
  position: absolute;
  left: -7px;
  top: -5px;
  background-color: rgb(255, 51, 51);
  border-radius: 50%;
  width: 23px;
  height: 23px;
  padding: 0px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-size: 13px;
}
.cart__btn img {
  width: 100%;
}

.item {
  background-color: #0000000e;
  border-radius: 7px;
  padding: 10px 15px;
  display: flex;
  flex-direction: column;
  row-gap: 15px;
}

.item__price {
  display: flex;
  justify-content: space-between;
}
.dec {
  border-bottom: 1px rgba(0, 0, 0, 0.11) solid;
  width: 45%;
  position: relative;
  bottom: 10px;
}
.btn {
  width: 100%;
  height: 40px;
  padding: 0;
}
.remove{
  width: 100px;
  height: 30px;
}
.wrapp__item {
  display: flex;
  flex-direction: column;
  row-gap: 25px;
  max-height: 620px;
  min-height: 600px;
  overflow: auto;
  margin-bottom: 15px;
  padding: 10px;
}
.wrapp{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 90%;
}
.finish {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    row-gap: 15px;
}
.all__price {
    display: flex;
    column-gap: 5px;
    justify-content: space-between;
}
.all__price p{
    font-size: 15px;
    width: 225px
}
.empty{
  position: absolute;
  left: 95px;
  top: 50dvh;
  font-size: 25px;
  font-weight: bold;
  color: rgba(0, 0, 0, 0.144);
}
@media(max-width: 650px){
  .item{
    font-size: 12px;
    row-gap: 10px;
  }
  .close{
    margin-bottom: 25px;
  }
  .wrapp__item {
    row-gap: 15px;
    max-height: 490px;
    min-height: 346px;
  }
}
</style>
