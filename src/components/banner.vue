<script setup>
import axios, { Axios } from 'axios'
import { ref } from 'vue'

const TOKEN = '7250082343:AAGL2tWYZx8CwHnenlknVyB-jc-R6z9-3Vk'
const URL_API = `https://api.telegram.org/bot${TOKEN}/sendMessage`
const CAHAT_ID = '-4552895886'
let email = ref('')
let showMessage = ref(false)

function sandEmail() {
  const nowData = new Date()
  const nowHours = nowData.getHours()
  const nowMinutes = nowData.getMinutes()

  let message = ref(`Заявка с сайта: \n Почта: ${email.value}\n Время: ${nowHours}:${nowMinutes}`)

  if (email.value) {
    try {
      axios.post(URL_API, {
        chat_id: CAHAT_ID,
        parse_mode: 'html',
        text: message.value
      })
      email.value = ''
      showMessage.value = true
      setTimeout(() => {
        showMessage.value = false
      }, 3000)
    } catch (error) {
      console.log(error)
      showMessage.value = false
    }
  }
}
</script>

<template>
  <div class="banner">
    <div class="text__left">
      <div class="number">
        <img src="/src/assets/image/phone.png" alt="phone" />
        <p>+7 999 99 99</p>
      </div>
      <p class="title">Позвоните нам</p>
      <p class="text">Если нужна помощь или нуждаетесь в консультации</p>
    </div>
    <form @submit.prevent="sandEmail">
      <p>Укажите свой Email</p>
      <input type="email" placeholder="Email" v-model="email" />
      <button type="submit" class="btn">записаться</button>
      <p class="succesSand" v-if="showMessage">Отправлено!</p>
    </form>
    <img src="/src/assets/image/callAuto.png" alt="car" class="banner__car" />
  </div>
</template>

<style scoped>
.banner {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  height: 317px;
  padding: 0 50px;
}
form {
  background-color: #fff;
  z-index: 10;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  border-radius: 20px;
  padding: 20px 40px;
  height: 250px;
  box-shadow: 0px 4px 25px 10px rgba(0, 0, 0, 0.06);
  position: relative;
}
form p {
  font-size: 22px;
}
form input {
  width: 490px;
  padding: 15px;
  border: none;
  border-radius: 20px;
  box-shadow: 0px 5px 19px -3px rgba(0, 0, 0, 0.21);
  background: rgb(255, 255, 255);
  font-size: 18px;
}
.text__left {
  padding-left: 230px;
  padding-top: 60px;
  background: url('/src/assets/image/leftArrow.png') 50% / cover no-repeat;
  color: #fff;
  position: absolute;
  left: 0;
  width: 960px;
  height: 317px;
  display: flex;
  flex-direction: column;
  row-gap: 10px;
}
.number {
  display: flex;
  align-items: center;
  font-size: 30px;
  font-weight: bold;
  margin-bottom: 20px;
}
.title {
  font-size: 30px;
  font-weight: bold;
}
.text {
  font-size: 15px;
  width: 350px;
  color: #ffffffa8;
}

.banner__car {
  width: 962px;
  height: 380px;
  position: absolute;
  right: -280px;
}
.btn {
  color: #fff;
}
.succesSand {
  position: absolute;
  top: -70px;
  background-color: #ececec;
  color: #000000;
  padding: 10px;
  font-size: 18px;
  border-radius: 10px;
}
@media (max-width: 1700px) {
  .text__left {
    padding-left: 50px;
  }
  .banner__car {
    width: 730px;
    height: 300px;
  }
  .text__left {
    width: 700px;
  }
}
@media (max-width: 1268px) {
  .text__left {
    display: none;
  }
  .banner__car {
    display: none;
  }
}
@media (max-width: 608px) {
  form input {
    width: 100%;
  }
  form {
    padding: 20px;
  }
}
</style>
