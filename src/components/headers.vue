<script setup>
import { ref } from 'vue'
import {isActiveCart} from './globalVar.js'
let isActive = ref(false)



</script>


<template>
  <header id="main">
    <div class="anim">
      <div class="ball_1"></div>
      <div class="ball_2"></div>
    </div>
    <div class="header__top">
      <div class="header_logo"><strong>AutoWorcks</strong></div>
      <img src="/src/assets/image/hamburger.png" alt="hamburger" class="h__menu" @click="isActive = !isActive">
      <div class="header__navigation" :class="{active: isActive}">
        <img src="/src/assets/image/close.png" alt="close" class="close" @click="isActive = !isActive">
        <nav>
          <a href="#main">Главная</a>
          <a href="#shop">Товары</a>
          <a href="#about">О нас</a>
          <a href="#" @click="isActiveCart = !isActiveCart"><button class="btn">Корзина</button></a>
        </nav>
      </div>
    </div>
    <div class="header__main">
      <h1>авторемонтная мастерская - это ваша <b>единственная</b> остановка</h1>
      <div class="wraoo">
        <a href="#shop"><button class="btn_two">Товары</button></a>
      </div>
    </div>
    <div class="bg"></div>
  </header>
</template>

<style scoped>
header {
  background: url('/src/assets/image/mainCar.png') 50% / cover no-repeat;
  min-height: 100dvh;
  position: relative;
  padding: 60px 75px;
  z-index: 1;
}
.bg {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background: rgb(255, 255, 255);
  background: linear-gradient(180deg, rgba(0, 0, 0, 0.26) 0%, rgba(0, 0, 0, 0.849) 100%);
  z-index: -1;
}
.header__top {
  display: flex;
  justify-content: space-between;
  z-index: 3;
}
.header_logo {
  color: rgb(255, 255, 255);
  font-size: 24px;
  cursor: pointer;
  letter-spacing: 3px;
}
.header__navigation nav {
  display: flex;
  align-items: center;
  column-gap: 50px;
}
.header__navigation nav a {
  font-size: 21px;
  color: #fff;
}
.header__navigation nav a:hover {
  color: #d6d6d6;
}

.header__main {
  padding-top: 200px;
  z-index: 3;
  display: flex;
  flex-direction: column;
  row-gap: 50px;
}
.header__main h1 {
  font-size: 65px;
  color: rgb(255, 255, 255);
  max-width: 850px;
}
.header__main h1 b {
  color: rgba(202, 24, 24, 0.507);
}
.btn_two {
  font-size: 20px;
}
a {
  width: 100%;
}

.anim {
  position: absolute;
  display: flex;
  left: 50px;
  bottom: 370px;
  rotate: 15deg;
  z-index: -1;
}
.ball_1 {
  width: 350px;
  height: 350px;
  background-color: rgba(255, 255, 255, 0.37);
  border-radius: 50%;
  filter: blur(50px);
  position: relative;
  animation: ball_1 7s linear infinite;
}
.ball_2 {
  background-color: rgba(255, 0, 0, 0.37);
  width: 350px;
  height: 350px;
  border-radius: 50%;
  filter: blur(50px);
  position: relative;
  animation: ball_2 7s linear infinite;
}
.h__menu{
  width: 45px;
  padding: 3px;
  background-color: #ffffff69;
  border-radius: 10px;
  display: none;
  cursor: pointer;
}
.close {
  width: 35px;
  position: absolute;
  top: 50px;
  left: 35px;
  cursor: pointer;
  display: none;
}

@keyframes ball_1 {
  0% {
    left: 0;
    z-index: 111;
  }
  50% {
    left: 380px;
  }
  100% {
    left: 0;
  }
}
@keyframes ball_2 {
  0% {
    right: 0;
  }
  50% {
    right: 380px;
  }
  100% {
    right: 0;
  }
}

@media (max-width: 900px) {
  .header__navigation nav {
    column-gap: 15px;
  }
  .header__navigation nav a {
    font-size: 17px;
  }
  .btn {
    width: 80px;
    font-size: 15px;
  }
  header{
    padding: 60px 25px;
  }
  .header__main h1{
    font-size: 45px;
  }
  .anim{
    left: 20px;
  }
  .ball_1, .ball_2 {
  width: 250px;
  height: 250px;
  }
}
@media (max-width: 575px) {
  .h__menu, .close{
    display: block;
  }
  .header__navigation{
    transition: .5s;
    position: fixed;
    right: -1000px;
    bottom: 0;
    top: 0;
    background-color: rgb(26, 26, 26);
    width: 100%;
    z-index: 500;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .header__navigation nav{
    display: flex;
    flex-direction: column;
    row-gap: 50px;
    text-align: center;
  }
  .header__navigation nav a{
    font-size: 30px;
  }
  .btn {
    width: 120px;
    font-size: 19px;
  }
  .header__main h1{
    font-size: 35px;
  }
}
.active {
  right: 0;
}
</style>
