<script setup>
import { ref } from 'vue'
</script>

<template>
  <div class="about__container" id="about">
    <p class="about__title">О нас</p>
    <p class="about__text">
      Мы компания - <b>Автосервис</b> которая специализируется на, починке и обслуживании авто.
    </p>
    <div class="car__info">
      <img class="car" src="/src/assets/image/car.png" alt="car" />
      <b class="r-info__text-1 row-t">Покраска кузова</b>
      <img class="r1 row" src="/src/assets/image/rowInfo.png" alt="rowInfo" />
      <b class="r-info__text-2 row-t">Полировка кузова</b>
      <img class="r2 row" src="/src/assets/image/rowInfo.png" alt="rowInfo" />

      <b class="r-info__text-3 row-t">Установка сабвуфера</b>
      <img class="r3 row" src="/src/assets/image/rowInfo.png" alt="rowInfo" />
      <b class="r-info__text-4 row-t">Замена колонок</b>
      <img class="r4 row" src="/src/assets/image/rowInfo.png" alt="rowInfo" />

      <b class="r-info__text-5 row-t">Полировка Дисок</b>
      <img class="r5 row" src="/src/assets/image/rowInfo.png" alt="rowInfo" />
      <b class="r-info__text-6 row-t">Замена Покрышек</b>
      <img class="r6 row" src="/src/assets/image/rowInfo.png" alt="rowInfo" />
    </div>
    <a href="#shop"><button class="btn">К услугам</button></a>
  </div>
</template>

<style scoped>
.about__container {
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
  justify-content: center;
  padding: 100px 0;
  padding-bottom: 200px;
  row-gap: 50px;
  border-bottom: 2px rgba(0, 0, 0, 0.045) solid;
}
.about__title {
  font-size: 40px;
}
.about__text {
  font-size: 45px;
  max-width: 1030px;
  margin-bottom: 100px;
}
.about__text b {
  color: rgb(202, 24, 24);
}
.car__info {
  position: relative;
}
.row {
  position: absolute;
  left: 0;
  bottom: 0;
}
.row-t{
    position: absolute;
  left: 0;
  bottom: 0;
}
.r1 {
  left: -300px;
  top: -30px;
}
.r2 {
  left: -300px;
  top: 30px;
}
.r-info__text-1 {
  left: -300px;
  top: -55px;
  font-size: 19px;
}
.r-info__text-2 {
  left: -300px;
  top: 5px;
  font-size: 19px;
}

.r3 {
  left: 110px;
  top: -40px;
}
.r4 {
  left: 110px;
  top: -0px;
}
.r-info__text-3 {
  left: 110px;
  top: -65px;
  font-size: 19px;
}
.r-info__text-4 {
  left: 110px;
  top: -25px;
  font-size: 19px;
}

.r5 {
  bottom: -50px;
  left: 730px;
  rotate: 180deg;
}
.r6 {
  bottom: -95px;
  left: 670px;
  rotate: 180deg;
}
.r-info__text-5 {
  bottom: -50px;
  left: 960px;
  width: 250px;
  font-size: 19px;
}
.r-info__text-6 {
  bottom: -95px;
  left: 910px;
  width: 200px;
  font-size: 19px;
}

@media (max-width: 1520px) {
  .car {
    width: 600px;
  }
  .r6 {
    left: 370px;
    bottom: -80px;
  }
  .r-info__text-6 {
    left: 610px;
    bottom: -80px;
  }
  .r5 {
    bottom: -27px;
    left: 375px;
  }
  .r-info__text-5 {
    bottom: -27px;
    left: 592px;
  }
  .r3 {
    left: 60px;
    top: -40px;
  }
  .r-info__text-3 {
    left: 45px;
  }
  .r4 {
    left: 34px;
    top: 0px;
  }
  .r-info__text-4 {
    left: 33px;
  }
}
@media (max-width: 1210px) {
  .car {
    width: 500px;
  }
  .row, .row-t {
    width: 200px;
    font-size: 11px;
    font-weight: normal;
  }
  .r6 {
    left: 200px;
    bottom: -20px;
  }
  .r-info__text-6 {
    left: 265px;
    bottom: -20px;
  }
  .r5 {
    bottom: 0px;
    left: 250px;
  }
  .r-info__text-5 {
    bottom: 0px;
    left: 315px;
  }
  .r3 {
    left: 100px;
    top: -20px;
  }
  .r-info__text-3 {
    left: 50px;
    top: -35px;
  }
  .r4 {
    left: 85px;
    top: 10px;
  }
  .r-info__text-4 {
    left: 30px;
    top: -5px;
  }
  
  .r1 {
    left: -46px;
    top: 10px;
  }
  .r-info__text-1 {
    left: -100px;
    top: -7px;
  }
  .r2 {
    left: -80px;
    top: 50px;
  }
  .r-info__text-2 {
    left: -130px;
    top: 32px;
  }

}
@media (max-width: 810px) {
    .about__text{
        font-size: 35px;
    }
}
@media (max-width: 690px) {
    .car{
        display: none;
    }
    .row{
        display: none;
    }
    .car__info{
        display: flex;
        flex-direction: column;
        row-gap: 20px;
    }
    .row-t {
        padding: 15px;
        width: 100%;
        position: static;
        font-weight: bold;
        font-size: 22px;
        border-top: 1px solid rgba(255, 0, 0, 0.103);
        border-radius: 5px;
        color: rgba(0, 0, 0, 0.699);
    }
    .row-t:nth-child(2){
        border: none;
    }
}

</style>
