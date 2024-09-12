<template>
  <div class="advantages">
    <div class="advantages__title">
      <b>Наши</b>
      <p>Преимущества</p>
    </div>
    <div class="flex__col">
      <div class="advantages__text__block">
        <div class="advantages__left fr">
          <div class="advantages__left__title"><h1>ВСЕ МАРКИ АВТОМОБИЛЕЙ</h1></div>
          <div class="advantages__text">
            <p>
              Мы предоставляем широкий спектр услуг по ремонту и техническому обслуживанию
              автомобилей всех марок и моделей, даже экзотических и винтажных.
            </p>
          </div>
        </div>
        <div class="advantages__right fr">
          <img src="/src/assets/image/line.png" alt="line" class="dec" />
        </div>
      </div>
      <div class="advantages__text__block">
        <div class="advantages__right fl">
          <img src="/src/assets/image/line.png" alt="line" class="dec" />
        </div>
        <div class="advantages__left fl">
          <div class="advantages__left__title"><h1>РАЗНООБРАЗИЕ УСЛУГ</h1></div>
          <div class="advantages__text">
            <p>
              Основным принципом нашей работы является предоставление широкого спектра качественных
              услуг по ремонту автомобилей, и мы делаем это с первого дня нашей работы.
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="flex__col">
      <div class="advantages__text__block">
        <div class="advantages__left fr">
          <div class="advantages__left__title"><h1>КАЧЕСТВЕННАЯ ПОДДЕРЖКА</h1></div>
          <div class="advantages__text">
            <p>
              Автосервис предлагает качественные программы технической поддержки для любых
              транспортных средств, которые позволяют им всегда оставаться полностью
              работоспособными.
            </p>
          </div>
        </div>
        <div class="advantages__right fr">
          <img src="/src/assets/image/line.png" alt="line" class="dec" />
        </div>
      </div>
      <div class="advantages__text__block">
        <div class="advantages__right fl">
          <img src="/src/assets/image/line.png" alt="line" class="dec" />
        </div>
        <div class="advantages__left fl">
          <div class="advantages__left__title"><h1>АКСЕССУАРЫ</h1></div>
          <div class="advantages__text">
            <p>
              В нашем автосервисе вы также можете приобрести любые необходимые аксессуары для вашего
              автомобиля, включая автомобильные шины и фильтры.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.advantages {
  padding: 250px 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  row-gap: 100px;
}
p::selection{
    background: #f3515194;
}
.advantages__title {
  display: flex;
  column-gap: 10px;
  font-size: 45px;
  color: rgba(0, 0, 0, 0.753);
}
.flex__col {
  display: flex;
  column-gap: 250px;
}
.advantages__text__block {
  display: flex;
  width: 573px;
  column-gap: 30px;
}
.advantages__left {
  display: flex;
  flex-direction: column;
  row-gap: 25px;
  justify-content: space-between;
}
.fr {
  text-align: end;
  align-items: end;
}
.fl {
  text-align: start;
  align-items: start;
}
.advantages__left__title {
  color: #b00000c0;
}
.advantages__text {
  color: rgba(0, 0, 0, 0.78);
  font-size: 26px;
}
.advantages__right {
    display: flex;
}
@media(max-width: 1500px){
  .flex__col{
    column-gap: 90px;
  }
  .advantages__left__title{
    font-size: 10px;
  }
  .advantages__text{
    font-size: 17px;
  }
  .advantages__text__block{
    width: 450px;
  }
}
@media(max-width: 1024px){
  .advantages__title{
    font-size: 35px;
  }
  .flex__col{
    column-gap: 70px;
  }
  .advantages__left__title{
    font-size: 7px;
  }
  .advantages__text{
    font-size: 15px;
  }
  .advantages__text__block{
    width: 300px;
  }
}
@media(max-width: 730px){
  .advantages__title{
    font-size: 30px;
  }
  .flex__col{
    flex-direction: column;
    row-gap: 150px;
  }
  .advantages__left__title{
    font-size: 12px;
  }
  .advantages__text{
    font-size: 20px;
  }
  .advantages__text__block{
    width: 100%;
  }
}
</style>
