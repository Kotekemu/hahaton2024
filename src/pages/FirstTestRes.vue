<template>
  <q-page style="background: #4DC5B0; overflow: hidden;">
    <div class = "title">
      <p class = "text"> Викторина </p>
    </div>
    <div>
      <q-chip class = "block" :ripple="false">
        <q-avatar>
          <img class = "img" src="~assets/icon.svg">
        </q-avatar>
        <p class = "textGame"> Ваш результат: {{  this.globalVariable }}</p>
        <p style = "white-space: normal; line-height: normal; text-align: center; color: #3A316A;">В современном цифровом мире важно быть внимательным к различным методам защиты информации и выявления угроз. Использование технологий, таких как VPN для защиты данных и многофакторной аутентификации для повышения безопасности аккаунтов, помогает предотвратить несанкционированный доступ. Также важно быть осторожным с электронными письмами и ссылками, чтобы избежать фишинга и других мошеннических схем. Применение общих принципов безопасности и осведомленность о возможных угрозах помогают защитить личную информацию и снизить риск вредоносных воздействий.</p>
      </q-chip>
    </div>
    <q-btn class = "menuButton" no-caps unelevated rounded :ripple="false" label="В меню" href="/#/menu/"/>
  </q-page>
</template>

<script>
import { Global } from 'src/global';
import option1Img from 'src/assets/krest.svg';
import option2Img from 'src/assets/galka.svg';
import defaultImg from 'src/assets/elli.svg';
export default {
  data() {
    return {
      selected: null,
      showBlock: false,
      option1Img,
      option2Img,
      defaultImg,
      globalVariable: Global.variable
    };
  },
  methods: {
    selectOption(option) {
      this.selected = option;
      this.showBlock = true;
    }
  }
}
</script>

<style lang="scss" scoped>
@media screen and (max-height: 740px) and (max-width: 400px) {
  .textGame {
    font-size: 14px !important;
    line-height: 20px !important;
    bottom: -3px;
  }
  .img {
    scale: 3 !important;
  }
  .textAnswer {
    font-size: 14px !important;
  }
}
  .img {
    position: absolute;
    scale: 4;
    top: -185px;
  }
  .title {
    background-color: #FAAA2E;
    border-radius: 0 0 30px 30px;
    height: 60px;
  }
  .text {
    font-family: Roboto;
    color: #3A316A;
    font-size: 45px;
    left: 50%;
    transform: translate(-50%, 0);
    position: absolute;
    top: -8px;
  }
  .block {
    background-color: #FAAA2E;
    max-width: 550px;
    width: 85%;
    height: 400px;
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
    top: 10px;
    FONT-WEIGHT: 600;
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
  .menuButton {
    max-width: 550px;
    width: 80%;
    position: absolute;
    left: 50%;
    transform: translate(-50%, 0);
    margin-top: 20px;
    background: #FAAA2E;
    color: #3A316A;
    font-family: Roboto;
    font-weight: 600;
    font-size: 18px;
  }
</style>