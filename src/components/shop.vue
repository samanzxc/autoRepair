<script setup>
import { ref } from 'vue'
import itemss from '/src/assets/items.json'
import cartList from './cart.vue'


let itemStorage = JSON.parse(localStorage.getItem('item'))
let items = ref([])
let cart = ref([])
let activeFilters = ref('all')
let resultPrice = ref(0)

if (itemStorage) {
  items.value = itemStorage
  updateCart()
} else {
  itemss.forEach((el) => {
    items.value.push(el)
  })
}

function addToCart(el) {
  el.isAdded = !el.isAdded
  cart.value = items.value.filter((item) => {
    return item.isAdded
  })

  let resultPriceArr = cart.value.map((el) => {
    return el.itemPrice
  })
  resultPrice.value = resultPriceArr.reduce((acc, el) => {
    acc += el
    return acc
  }, 0)
  localStorage.setItem('item', JSON.stringify(items.value))
}

function updateCart(){
  cart.value = items.value.filter((item) => {
    return item.isAdded
  })
  let resultPriceArr = cart.value.map((el) => {
    return el.itemPrice
  })
  resultPrice.value = resultPriceArr.reduce((acc, el) => {
    acc += el
    return acc
  }, 0)
}
</script>

<template>
  <div class="shop__container" id="shop">
    <div class="shop__title"><p>Наши товары и услуги</p></div>
    <div class="item__block">
      <div class="item__filter">
        <span @click="activeFilters = 'all'" :class="{ active: activeFilters === 'all' }">Все</span>
        <span @click="activeFilters = 'whell'" :class="{ active: activeFilters === 'whell' }"
          >Колёса</span
        >
        <span @click="activeFilters = 'body'" :class="{ active: activeFilters === 'body' }"
          >Кузов</span
        >
        <span @click="activeFilters = 'music'" :class="{ active: activeFilters === 'music' }"
          >Акустика</span
        >
      </div>
      <div class="items">
        <div
          class="item"
          v-for="(item, index) in items"
          :key="index"
          v-show="activeFilters === item.category || activeFilters === 'all'"
        >
          <img :src="item.img" alt="wheel" class="item__img" />
          <div class="item__body">
            <div class="wrapp">
              <div class="item__title">
                <b>{{ item.itemName }}</b>
              </div>
              <div class="item__price">
                <p>Стоимость:</p>
                <span>{{ item.itemPrice }}₽</span>
              </div>
            </div>
            <button class="btn" @click="addToCart(item)" :class="{ added: item.isAdded == true }">
              В корзину
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
  <cartList :cart="cart" 
  :items="items" 
  :addToCart="addToCart" 
  :resultPrice="resultPrice" 
  />
</template>

<style scoped>
.shop__container {
  padding: 100px 0;
}
.shop__title {
  color: rgba(0, 0, 0, 0.77);
  font-size: 36px;
  text-align: center;
  margin-bottom: 100px;
}
.item__block {
  display: flex;
  flex-direction: column;
  row-gap: 75px;
}
.item__filter {
  padding-left: 50px;

  display: flex;
  column-gap: 20px;
  font-size: 20px;
  font-weight: bold;
}
.item__filter span {
  cursor: pointer;
}
.items {
  display: flex;
  flex-wrap: wrap;
  gap: 170px;
  align-items: center;
  justify-content: center;
}
.item {
  display: flex;
  column-gap: 50px;
  width: 385px;
  height: 150px;
}
.item__img {
  width: 145px;
  position: relative;
}
.bd {
  height: 145px;
}

.item__body {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.item__body::before {
  content: '';
  position: absolute;
  background-color: rgb(0, 0, 0);
  left: -30px;
  top: 0;
  bottom: 0;
  width: 3px;
}
.item__title {
  font-size: 18px;
  font-weight: bold;
}
.item__price {
  display: flex;
  column-gap: 15px;
}
.item__price span {
  color: black;
  font-weight: bold;
  font-size: 18px;
}

.item__filter span:hover {
  opacity: 0.7;
}
.active {
  border-bottom: 2px black solid;
}
.added {
  background-color: rgba(0, 0, 0, 0.623);
}
@media (max-width: 490px) {
  .item__filter {
    padding: 0;
    justify-content: center;
    column-gap: 20px;
  }
  .item__img {
    width: 100px;
    height: 100px;
  }
  .item {
    width: 340px;
    display: flex;
    align-items: center;
  }
  .wrapp {
    margin-bottom: 20px;
  }
}
</style>
