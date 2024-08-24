<template>
  <q-page style="background: #4DC5B0; overflow: hidden;">
    <div class = "title">
      <p class = "text"> peepoHey application for "СИТЕК" </p>
    </div>
    <div class = "xz">
      <q-btn no-caps class = "buton4ik" color="white" label="Тесты" />
      <q-btn no-caps class = "buton4ik" color="white" label="Проверка сайта" />
      <q-btn no-caps class = "buton4ik" color="white" label="Проверка пароля" />
      <q-btn no-caps class = "buton4ik" color="white" label="Безопасность телефона" />
      <q-btn no-caps class = "buton4ik" color="white" label="Проверка номера телефона" />

    </div>
  </q-page>
</template>

<script>

</script>

<style lang="scss" scoped>
  .buton4ik {
    margin-top: 20px;
    border-radius: 25px;
    height: 55px;
    font-size: 20px;
    font-family: Roboto;
    color: #3A316A !important;
  }
  .xz {
    display: grid;
      width: 90%;
      max-width: 550px;
      position: absolute;
      left: 50%;
      transform: translate(-50%, 0);
      margin-top: 20px;
  }
  .img {
    position: absolute;
    scale: 4;
    top: -60px;
    left: -5px;
  }
  .title {
    background-color: #FAAA2E;
    border-radius: 0 0 30px 30px;
    height: 60px;
  }
  .text {
    font-family: Roboto;
    color: #3A316A;
    font-size: 20px;
    left: 50%;
    transform: translate(-50%, 0);
    position: absolute;
    width: 100%;
    text-align-last: center;
    font-weight: 600;
  }
  .block {
    background-color: #FAAA2E;
    max-width: 550px;
    width: 85%;
    height: 120px;
    border-radius: 30px;
    left: 50%;
    transform: translate(-50%, 0);
    align-content: center;
    margin-top: 50px;
  }
  .textGame {
    text-align: center;
    width: 100%;
    font-size: 20px;
    font-family: Roboto;
    line-height: 25px;
    max-width: 550px;
    white-space: break-spaces;
    left: 0;
    position: absolute;
    color: #3A316A;
  }
  .button {
    background: #FAAA2E;
    left: 50%;
    transform: translate(-50%, 0);
    margin-top: 15px;
    max-width: 550px;
    width: 85%;
    border-radius: 30px;
  }
  .textAnswer {
    font-family: Roboto;
    color: #3A316A;
    text-transform: none;
    font-size: 20px;
    font-weight: 400;
  }
</style>