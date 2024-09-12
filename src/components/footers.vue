<template>
  <footer>
    <b>AutoWorcks</b>
    <p>Все права защищены 2024©</p>
  </footer>
</template>

<style scoped>
footer {
  padding: 20px 100px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: rgba(0, 0, 0, 0.11);
  color: rgba(0, 0, 0, 0.24);
  font-size: 16px;
}
footer b{
  font-size: 20px;
}
@media(max-width: 570px){
  footer{
    padding: 20px;
    font-size: 14px;
  }
  footer b{
  font-size: 15px;
}
}
</style>
